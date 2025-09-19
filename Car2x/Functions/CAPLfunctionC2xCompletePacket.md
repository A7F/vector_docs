# C2xCompletePacket

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long C2xCompletePacket( long packet );
```

## Description

This function completes a packet before sending it with [C2xOutputPacket](CAPLfunctionC2xOutputPacket.md). It calculates the fields that are marked with **CompleteProtocol** in the protocol overview, e.g. checksum, lengths, etc.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md).

## Return Values

- **0**: No error, OK
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

See example of [C2xInitPacket](CAPLfunctionC2xInitPacket.md).

