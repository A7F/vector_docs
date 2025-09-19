# C2xAddToken

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xAddToken( long packet, char protocolDesignator[], char tokenDesignator[] );
```

## Description

This function adds an additional token at the end of a protocol header.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md)
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md)
- **tokenDesignator**: Name of the token

## Return Values

- **0**: No error, OK
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
long packetHandle = 0;
packetHandle = C2xInitPacket("wsmp");
C2xAddToken(packetHandle, "wsmp", "transmitPower");
C2xAddToken(packetHandle, "wsmp", "dataRate");
C2xAddToken(packetHandle, "wsmp", "channelNumber");
C2xCompletePacket(packetHandle);
C2xOutputPacket(packetHandle);
```
