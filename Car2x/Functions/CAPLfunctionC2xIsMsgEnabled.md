# C2xIsMsgEnabled

[CAPL Functions](../../CAPLfunctions.md) » Car2x » C2xIsMsgEnabled

**Valid for:** CANoe DE

## Function Syntax

- `long C2xIsMsgEnabled (char* dbMessage); //form 1`
- `long C2xIsMsgEnabled (char* dbMessage, char* stationName); //form 2`
- `long C2xIsMsgEnabled (long packetHandle); // form 3`
- `long C2xIsMsgEnabled (char stationName[], long packetHandle); // form 4`

## Description

Check if a message is enabled for cyclic sending.

## Parameters

- **dbMessage**: Name of the message to check.
- **stationName**: Name of the sending station.
- **packetHandle**: Packet handle of the message to check.

## Return Values

- **1**: True
- **0**: False
- **-1**: Error

## Example

```plaintext
LONG result = 0;
long packetHdl = -1;
result = C2xIsMsgEnabled("CAM");

packetHdl = C2xGetMessageHandle (1,1);
result = C2xIsMsgEnabled (packetHdl);

result = C2xIsMsgEnabled ("BasicNode",packetHdl);
```
