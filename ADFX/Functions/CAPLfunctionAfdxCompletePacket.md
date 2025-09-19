# AfdxCompletePacket

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxCompletePacket( long packet );
```

## Description

This function completes a packet before sending it with [AfdxOutputPacket](CAPLfunctionAfdxOutputPacket.md). It calculates the fields that are marked with **CompleteProtocol** in the protocol overview, e.g. checksum, lengths, etc.

A frame needs to be completed prior to transmission. This is the case when one of the header fields is changed in an existing frame or the payload size is changed afterwards. With this function the checksum and length fields in the [UDP](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolUDP.md) and [IPv4](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolIPv4.md) header are calculated and filled in.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).

## Return Values

- **0**: Frame is successfully completed.
- **other value**: See [error code](../CAPLfunctionsAFDXErrorCodes.md).

## Example

See example of [AfdxResizeToken](CAPLfunctionAfdxResizeToken.md).
