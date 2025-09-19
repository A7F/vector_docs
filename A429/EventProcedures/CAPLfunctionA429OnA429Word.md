# on a429word

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
CAPL programs are by default not transparent to bus events. This means that a CAPL node in the evaluation branch of the measurement setup will block the data flow to its right side. You must explicitly code the forwarding of messages in CAPL nodes in the evaluation branch. In order to re-use this code snippet in Simulation Setup of your CANoe DE product you have to add conditional compilation. Otherwise a recursion will occur.

Forward ARINC word event:

```plaintext
on a429word * {
  #if MEASUREMENT_SETUP
  output(this);
  #endif
}
```

## Description

The event procedure `on a429word` is called on every event, related to an error free ARINC word. Additional information related to this event is available via the [selectors](../CAPLfunctionsA429Selectors.md). The key word [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md) is available within an `on a429word` procedure, to access the data of the ARINC word event that has just been received.

## Selectors

- **a429word**: More information about [a429word](../CAPLfunctionsA429DefineARINCword.md).

## Example

| Example                      | Triggering ARINC word event                                  |
|------------------------------|--------------------------------------------------------------|
| `on a429word 0x43`           | Event with label = 0x43 (dec. = 67, oct. = 103o)             |
| `on a429word 67`             | Event with label = 67 (hex. = 0x43, oct. = 103o)             |
| `on a429word LBL_103`        | Event with label from assigned database                      |
| `on a429word *`              | Event with any label                                         |
| `on a429word MsgChannel7.*`  | Event with any label on channel 7                            |
| `on a429word MsgChannel7.67` | Event with label = 67 (hex. = 0x43, oct. = 103o) on channel 7|
| `on a429word 2, 0x30..0x38`  | Event with label = 2, 48..56                                 |
| `on a429word MsgChannel7.LBL_103` | Event with label from assigned database on channel 7    |

