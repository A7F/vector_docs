# AfdxReleasePacket

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxReleasePacket( long packet );
```

## Description

This function deletes a packet created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md). The handle can not be used any longer.

## Parameters

- **packet**: Handle of the message to delete.

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

See example of [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md)
