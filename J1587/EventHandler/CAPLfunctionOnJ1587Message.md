[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1587/EventHandler/CAPLfunctionOnJ1587Message.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1587](../CAPLfunctionsJ1587Overview.md) » on J1587Message

# on J1587Message

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Description

Defines the event handler for a valid J1708 message, the `this` pointer is of type [J1587Message](../../../Shared/CAPL/General/J1587Message.md).

For passing this message to other node, `output(this)` must be called inside the event handler.

## Parameters

dbNode | MID | * // Msg with J1587_Error = 0

## Example

**on J1587Message** 50 // 50 is Sender MID, can be dbNode name or MID

```
{
  J1587Param 0 param;
  if (GetParameterByPID(this, 30, param) == 0)
  {
    output(this);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
