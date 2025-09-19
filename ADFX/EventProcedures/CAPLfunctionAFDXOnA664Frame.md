# on a664Frame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

CAPL programs are by default not transparent to bus events. This means that a CAPL node in the evaluation branch of the measurement setup will block the data flow to its right side. You must explicitly code the forwarding of messages in CAPL nodes in the evaluation branch. In order to re-use this code snippet in the Simulation Setup of your CANoe DE product you have to add conditional compilation. Otherwise a recursion will occur.

Forward AFDX packet event:

```
on a664Frame * {
  #if MEASUREMENT_SETUP
  output(this);
  #endif
}
```

## Function Syntax

```
on a664Frame <virtual link>|ICMP
```

## Description

The event procedure **on a664Frame** is called on every AFDX packet if the following conditions are fulfilled:

- The virtual link id corresponds to the given id (asterisk means "any virtual link").
- The packet is not reassembled.

or

- The frame is an ICMP frame.

Additional information related to this event is available via the [selectors](../CAPLfunctionsAFDXSelectors.md). The keyword [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md) is available within an **on a664Frame** procedure to access the data of the AFDX event that has just been received.

## Selectors

[Selectors for AFDX-Frames](../CAPLfunctionsAFDXSelectors.md)

## Example

Calling conventions for the **on a664Frame** handler.

- `on a664Frame 0xA1`: Event with VLId 0xA1 (hexadecimal).
- `on a664Frame 123`: Event with VLId 123 (decimal).
- `on a664Frame *`: Event with any VLId.
- `on a664Frame MsgChannel1.*`: Event with any VLId on channel 1.
- `on a664Frame MsgChannel1.0xA1`: Event with VLId 0xA1 (hexadecimal) on channel 1.
- `on a664Frame MsgChannel1.123`: Event with VLId 123 (decimal) on channel 1.
- `on a664Frame ICMP`: ICMP Event on any channel.
- `on a664Frame MsgChannel1.ICMP`: ICMP Event on channel 1.

