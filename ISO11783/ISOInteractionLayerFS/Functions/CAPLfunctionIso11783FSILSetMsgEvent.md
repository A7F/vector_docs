[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILSetMsgEvent.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_SetMsgEvent**

# FSIL_SetMsgEvent

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_SetMsgEvent( dbMsg msg ); // form 1
long FSIL_SetMsgEvent( dbNode fs, dbMsg msg ); // form 2
```

## Description

The message is sent immediately, the send type is ignored. The FS IL must be in state **active** and the message must be assigned to the node as Tx message.

To modify signal values prior to message transmission, the CAPL functions [FSIL_SetSignal](CAPLfunctionIso11783FSILSetSignal.md) or [FSIL_SetSignalRaw](CAPLfunctionIso11783FSILSetSignalRaw.md) can be used.

## Parameters

- **msg**: Message name from database. The message must be a Tx message of the node.
- **fs**: FS simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 'i'
{
    FSIL_SetMsgEvent( ICC_FS );
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)