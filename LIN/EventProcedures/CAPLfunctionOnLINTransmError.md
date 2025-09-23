[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/EventProcedures/CAPLfunctionOnLINTransmError.md)

**CAPL Functions** » **LIN** » **on linTransmError**

# on linTransmError

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Description

The event procedure `on linTransmError` is called when no Slave responded to a transmission request.

The keyword `this` and the selectors (see Option .LIN: linTransmError selectors) can be used to access the data of the event that has just been received.

## Selectors

- [linTransmError](../Selectors/CAPLfunctionLINTransmError.md)

## Example

Handle transmission error for a certain frame on channel 1:

```plaintext
on linTransmError
{
    if (this.MsgChannel == 1 && this.ID == 0x33) {
        …
    }
}
```
