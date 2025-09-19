# C2xDisableMsg

[CAPL Functions](../../CAPLfunctions.md) » Car2x » C2xDisableMsg

**Valid for**: CANoe DE

## Function Syntax

- `long C2xDisableMsg (char* dbMessage); //form 1`
- `long C2xDisableMsg (char* dbMessage, char* stationName); //form 2`
- `long C2xDisableMsg(long packetHandle); // form 3`
- `long C2xDisableMsg(char stationName[], long packetHandle); // form 4`

## Description

Disables a message for which the database attribute Send Type is Cyclic or CyclicIfActive in the database for cyclic sending. The function has no effect for messages with Send Type NoMsgSendType.

## Parameters

- **dbMessage**: Name of the message to be disabled.
- **stationName**: Name of the sending station.
- **packetHandle**: Packet handle of the message to be disabled.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```c
long packetHdl =  -1;
C2xDisableMsg("CAM");
packetHdl = C2xGetMessageHandle(1,1);
C2xDisableMsg(packetHdl);
C2xDisableMsg("BasicNode",packetHdl);
```
