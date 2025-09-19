[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1587/EventHandler/CAPLfunctionOnJ1587ErrorMessage.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1587](../CAPLfunctionsJ1587Overview.md) » on J1587ErrorMessage

# on J1587ErrorMessage

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Description

Defines the event handler for an erroneous J1708 message. The error code is contained in `J1587ErrorMessage::J1587_Error`.

For passing this message to other node, `output(this)` must be called inside the event handler.

## Parameters

- - (receives all MIDs) // Msg with J1587_Error != 0

## Example

**on J1587ErrorMessage** 50 //50 is Sender MID, can be dbNode name or MID

```
{
  write ("Msg with ErrorCode %d received, MID %d", this.J1587_MID,
  this.J1587_Error);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
