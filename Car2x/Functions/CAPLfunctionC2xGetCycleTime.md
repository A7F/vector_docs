# C2xGetCycleTime

[CAPL Functions](../../CAPLfunctions.md) » Car2x » C2xGetCycleTime

Valid for: CANoe DE

## Function Syntax

- `Int64 C2xGetCycleTime(char* dbMessage);` //form 1
- `Int64 C2xGetCycleTime(char* dbMessage, char* stationName);` //form 2
- `Int64 C2xGetCycleTime (long packetHandle);` // form 3
- `Int64 C2xGetCycleTime (char stationName[], long packetHandle);` // form 4

## Description

Gets the cycle time for a message in milliseconds.

## Parameters

- **dbMessage**: Name of the message
- **stationName**: Name of the sending station
- **packetHandle**: Packet handle of the message to be disabled.

## Return Values

- **Cycle time**: Cycle time in milliseconds
- **-1**: Error

## Example

```plaintext
Int64 cycleTime;
long packetHdl;

cycleTime = C2xGetCycleTime("CAM");

packetHdl = C2xGetMessageHandle (1,1);

cycleTime = C2xGetCycleTime (packetHdl);
cycleTime = C2xGetCycleTime ("BasicNode", packetHdl);
```
