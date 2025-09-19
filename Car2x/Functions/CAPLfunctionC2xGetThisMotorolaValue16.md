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
