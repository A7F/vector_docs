# GetBusNameContext

[Valid for: CANoe DE • CANoe4SW DE](../../../Shared/FeatureAvailability.md)

**Note**

The bus context plays a role in modeling gateways and in tests of control units with several [bus connections](../../../Shared/CAPL/General/TestMultiBusEnvironment.md). In this case, a series of CAPL functions such as [canOnline](CAPLfunctionCanOnline.md) and [canOffline](CAPLfunctionCanOffline.md) may have more than one meaning in terms of the network interface (channel) to be used. A similar type of problem occurs when identical node layer modules are used simultaneously within a CAPL block. A distinction must be made between the instances of the node layer, both for calls to CAPL functions that are implemented in the node layers and for implementing callbacks.

To facilitate this distinction, a bus context is placed in the CAPL program by the runtime environment while a callback is being executed by the node layer. This context unambiguously identifies the node layer that is making the call. In a similar manner, the call of a CAPL function that is implemented in a node layer is forwarded on to the appropriate node layer, depending on the current bus context. This also applies to the CAPL functions mentioned above, [canOnline](CAPLfunctionCanOnline.md) and [canOffline](CAPLfunctionCanOffline.md), as well as to many [wait points](../../../CANoeCANalyzer/Test/TestFeatureSet/TFSWait.md) of the [Test Feature Set](../../../CANoeCANalyzer/Test/TestFeatures.md).

You should use the functions [GetBusNameContext](#), `GetBusContext` and [SetBusContext](CAPLfunctionSetBusContext.md) to determine the context of a bus, to query or to change the current bus context.

## Function Syntax

```plaintext
dword GetBusNameContext(char name[]); // form 1
dword GetBusNameContext(dword busType, dword channelNumber); // form 2
```

## Description

Returns the context of the specified bus.

## Parameters

- **name**: The name of the bus. The bus name can be taken from the CANoe DE product [Simulation Setup](../../../CANoeCANalyzer/Windows/SimulationSetup/SimulationSetupWindow.md):
  1. Open the [System View](../../../CANoeCANalyzer/Windows/SimulationSetup/SimulationSetupWindowShortcutMenu.md)
  2. Select a network
  3. Select the **Rename...** shortcut menu command
  4. Copy the name from the dialog

- **busType**: Bus system of the bus. The predefined enum BusType should be used for the value of this parameter.

- **channelNumer**: Number of the channel for the specified bus. Channel numbering starts with 1.

## Return Values

- In the case of success, the context of the specified bus is returned.
- If the specified bus does not exist, 0 is returned.

## Example

This is an example for a **simulation node**. Test nodes should copy the bus context to a CAPL variable in the `Main()` function because all global variables are cleared when a test module is started.

```plaintext
variables
{
    char ibus[32] = "ibus";
    char motbus[32] = "motbus";

    dword ibus_context = 0;
    dword motbus_context = 0;
}
on preStart
{
    ibus_context = GetBusNameContext(ibus);
    motbus_context = GetBusNameContext(motbus);

    if (0 == ibus_context)
    {
        writeex(0, 3, "Error: Cannot determine context for bus: %s", ibus);
    }
    if (0 == motbus_context)
    {
        writeex(0, 3, "Error: Cannot determine context for bus: %s", motbus);
    }
}
```

[GetBusContext](CAPLfunctionGetBusContext.md) • [SetBusContext](CAPLfunctionSetBusContext.md)
