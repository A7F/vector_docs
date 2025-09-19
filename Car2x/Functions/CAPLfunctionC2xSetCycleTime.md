[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetCycleTime.md)

## C2xSetCycleTime

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSetCycleTime

**Valid for**: CANoe DE

### Function Syntax

- `long C2xSetCycleTime(char* dbMessage, int64 milliseconds); //form 1`
- `long C2xSetCycleTime(char* dbMessage, int64 milliseconds, char* stationName); //form 2`
- `long C2xDisableMsg(long packetHandle, int64 milliseconds); // form 3`
- `long C2xDisableMsg(char stationName[], long packetHandle, int64 milliseconds); // form 4`

### Description

Sets the cycle time for a message.

### Parameters

- **dbMessage**: Name of the message.
- **milliseconds**: New cycle time in milliseconds.
- **stationName**: Name of the sending station.
- **packetHandle**: Packet handle of the message to check.

### Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

### Example

```c
long packetHdl = -1;
C2xSetCycleTime("CAM", 1000);

packetHdl = C2xGetMessageHandle (1,1);
C2xSetCycleTime (1000, packetHdl);

C2xSetCycleTime ("BasicNode", 1000, packetHdl);
```

[See Also](javascript:void(0);)
