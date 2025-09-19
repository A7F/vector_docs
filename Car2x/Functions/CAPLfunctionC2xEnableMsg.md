[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xEnableMsg.md)

## C2xEnableMsg

[CAPL Functions](../../CAPLfunctions.md) » Car2x » C2xEnableMsg

**Valid for:** CANoe DE

### Function Syntax

- `long C2xEnableMsg (char* dbMessage); //form 1`
- `long C2xEnableMsg (char* dbMessage, char* stationName); //form 2`
- `long C2xEnableMsg(long packetHandle); // form 3`
- `long C2xEnableMsg (char stationName[], long packetHandle); // form 4`

### Description

Enables a message for which the database attribute Send Type is Cyclic or CyclicIfActive in the database for cyclic sending. The function has no effect for messages with Send Type NoMsgSendType.

### Parameters

- **dbMessage**: Name of the message to be enabled
- **stationName**: Name of the sending station
- **packetHandle**: Packet handle of the message to be enabled.

### Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

### Example

```c
long packetHdl =  -1;
C2xEnableMsg("CAM");
packetHdl = C2xGetMessageHandle(1,1);
C2xEnableMsg(packetHdl);
C2xEnableMsg ("BasicNode",packetHdl);
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
