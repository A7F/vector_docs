[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxSetTokenInt64.md)

**CAPL Functions** » **AFDX** » **AfdxSetTokenInt64**

# AfdxSetTokenInt64

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxSetTokenInt64( long packet, char protocolDesignator[], char tokenDesignator[], int64 value ); // form 1
long AfdxSetTokenInt64( long packet, char protocolDesignatorl[], char tokenDesignator[], long offset, long length, long networkByteOrder, int64 value ); // form 2
```

## Description

This function sets the specified token‘s data to a new 64-bit integer value. With additional parameters (form 2) the user may specify the starting byte, length and byte ordering of the integer value in the token.

**Note**: The network byte order interpretation for form 1 is big-endian.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md), e.g. "afdx".
- **tokenDesignator**: Name of the token, e.g. "lpvSpeed".
- **offset**: This is the offset from the beginning of the token's data area. If this is 0, data is copied starting at byte 0 of the token's data area.
- **length**: This is the length of the integer value to be copied to the token's data area (range 1..8).
- **networkByteOrder**:
  - 0: INTEL (little-endian)
  - 1: MOTOROLA (big-endian)
- **value**: New integer value.

## Return Values

- **0**
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

See example of [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)