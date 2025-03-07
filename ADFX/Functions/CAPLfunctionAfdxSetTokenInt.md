# AfdxSetTokenInt

[CAPL Functions](../../CAPLfunctions.md) » [AFDX](../CAPLfunctionsAFDXOverview.md) » AfdxSetTokenInt

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxSetTokenInt( long packet, char protocolDesignator[], char tokenDesignator[], long value ); // form 1
long AfdxSetTokenInt( long packet, char protocolDesignatorl[], char tokenDesignator[], long offset, long length, long networkByteOrder, long value ); // form 2
```

## Description

This function sets the specified token‘s data to a new integer value. With additional parameters (form 2) the user may specify the starting byte, length, and byte ordering of the integer value in the token.

**Note**: The network byte order interpretation for form 1 is big-endian.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md), e.g. "afdx".
- **tokenDesignator**: Name of the token, e.g. "lpvSpeed".
- **offset**: This is the offset from the beginning of the token's data area. If this is 0, data is copied starting at byte 0 of the token's data area.
- **length**: This is the length of the integer value to be copied to the token's data area (range 1..4).
- **networkByteOrder**:
  - 0: INTEL (little-endian)
  - 1: MOTOROLA (big-endian)
- **value**: New integer value.

## Return Values

- **0**
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

See example of [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md)

[See Also](javascript:void(0);)