# C2xGetThisMotorolaValue64

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetThisMotorolaValue64.md)

**CAPL Functions** » **Car2x** » C2xGetThisMotorolaValue64

**Valid for**: CANoe DE

**Note**: This function is only usable in a CAPL callback that had been registered with [C2xReceivePacket](CAPLfunctionC2xReceivePacket.md).

## Function Syntax

```plaintext
long C2xGetThisMotorolaValue64( long offset );
```

## Description

This function reads the data of a received packet in Motorola format.

## Parameters

- **offset**: Byte offset relative to the beginning of a data packet or the payload.

## Return Values

Read value.

## Example

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  QWORD value64;
  value64 = C2xGetThisMotorolaValue64( 0 );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)