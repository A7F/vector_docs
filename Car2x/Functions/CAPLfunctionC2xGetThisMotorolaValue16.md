[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetThisMotorolaValue16.md)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetThisMotorolaValue16

# C2xGetThisMotorolaValue16

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only usable in a CAPL callback that had been registered with [C2xReceivePacket](CAPLfunctionC2xReceivePacket.md).

## Function Syntax

```plaintext
long C2xGetThisMotorolaValue16( long offset );
```

## Description

This function reads the data of a received packet in Motorola format.

## Parameters

- **offset**: Byte offset relative to the beginning of a data packet or the payload (see description above).

## Return Values

Read value.

## Example

```c
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  WORD value16;
  value16 = C2xGetThisMotorolaValue16( 0 );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)