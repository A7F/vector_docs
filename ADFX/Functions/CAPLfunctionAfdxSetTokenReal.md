# AfdxSetTokenReal

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxSetTokenReal.md)

**CAPL Functions** » **AFDX** » AfdxSetTokenReal

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxSetTokenReal( long packet, char protocolDesignator[], char tokenDesignator[], long offset, long length, float value );
```

## Description

This function sets the specified token‘s data as a [float](../../../Shared/CAPL/General/DataTypesForFunctionParameters.md) value.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md), e.g. "udp".
- **tokenDesignator**: Name of the token, e.g. "data".
- **offset**: This is the offset from the beginning of the token's data area. If this is 0, data is copied starting at byte 0 of the token's data area.
- **length**: The values 4 (32-bit float value) and 8 (64-bit float value) are allowed here. This is the length of the value to be copied to the token's data area.
- **value**: New value.

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

```plaintext
{
  // have a packet handle <packet> created already
  long err = 0;
  err = AfdxSetTokenReal( packet, "udp", "data", 8, 8, 1.234);
}
```
