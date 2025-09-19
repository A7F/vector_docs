[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetBusContext.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » SetBusContext

# SetBusContext

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
The bus context plays a role in modeling gateways and in tests of control units with several [bus connections](../../../Shared/CAPL/General/TestMultiBusEnvironment.md). In this case, a series of CAPL functions such as [canOnline](CAPLfunctionCanOnline.md) and [canOffline](CAPLfunctionCanOffline.md) may have more than one meaning in terms of the network interface (channel) to be used. A similar type of problem occurs when identical node layer modules are used simultaneously within a CAPL block. A distinction must be made between the instances of the node layer, both for calls to CAPL functions that are implemented in the node layers and for implementing callbacks.

To facilitate this distinction, a bus context is placed in the CAPL program by the runtime environment while a callback is being executed by the node layer. This context unambiguously identifies the node layer that is making the call. In a similar manner, the call of a CAPL function that is implemented in a node layer is forwarded on to the appropriate node layer, depending on the current bus context. This also applies to the CAPL functions mentioned above, [canOnline](CAPLfunctionCanOnline.md) and [canOffline](CAPLfunctionCanOffline.md), as well as to many [wait points](../../../CANoeCANalyzer/Test/TestFeatureSet/TFSWait.md) of the [Test Feature Set](../../../CANoeCANalyzer/Test/TestFeatures.md).

You should use the functions [GetBusNameContext](CAPLfunctionGetBusNameContext.md), [GetBusContext](CAPLfunctionGetBusContext.md) and `SetBusContext` to determine the context of a bus, to query the current bus context, or to change the context.

## Function Syntax

```
dword SetBusContext( dword context);
```

## Description

Sets the bus context of the CAPL block.

## Parameters

- **context**: The new bus context to be set.

## Return Values

The bus context that was valid before the call was made is returned.

## Example

This is an example for a **simulation node**.  
Test nodes should copy the bus context to a CAPL variable in the `Main()` function because all global variables are cleared when the test module is started.

```plaintext
variables
{
    dword ibus_context = 0;
    dword motbus_context = 0;
}
on preStart
{
    ibus_context = GetBusNameContext( "ibus");
    motbus_context = GetBusNameContext( "motbus");
}
void apCanOn()
{
    dword context;
    // activate the CAN channel on the "current" context
    CanOnline();
    // determine the "other" context
    context = ibus_context == GetBusContext() ? motbus_context : ibus_context;
    // set the context to the "other" bus...
    SetBusContext( context);
    // ...and activate its CAN chip as well
    CanOnline();
}
```

[GetBusNameContext](CAPLfunctionGetBusNameContext.md) • [GetBusContext](CAPLfunctionGetBusContext.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
