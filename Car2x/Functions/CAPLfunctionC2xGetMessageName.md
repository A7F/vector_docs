# C2xGetMessageName

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetMessageName.md)

[CAPL Functions](../../CAPLfunctions.md) » Car2x » C2xGetMessageName

**Valid for**: CANoe DE

## Function Syntax

```
long C2xGetMessageName(long packetHandle, long bufferSize, char buffer[])
```

## Description

Get the application layer (topmost interpreted layer) name of a received message.

## Parameters

- **packetHandle**: Handle of a packet.
- **bufferSize**: Maximum number of bytes to be copied.
- **buffer**: Buffer in which the name is copied.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```c
void OnRxPacket(long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet)
{
  char messageName[128];
  C2xGetMessageName(packet, elcount(messageName), messageName);
  if (!strncmp("CAM", messageName, elcount(messageName)))
  {
    //...
  }
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)