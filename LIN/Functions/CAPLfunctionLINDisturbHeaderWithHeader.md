[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINDisturbHeaderWithHeader.md)

**CAPL Functions** » **LIN** » **linDisturbHeaderWithHeader**

# linDisturbHeaderWithHeader

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linDisturbHeaderWithHeader(dword byteIndex, dword bitIndex, long disturbingFrameId);
```

## Description

Configures the LIN hardware to disturb the next header with a new header (id=<disturbanceHeaderID>).

## Parameters

- **byteIndex**: 
  - Starts disturbance in byte with index `<byteIndex>`.
  - 0: Sync Byte
  - 1: ProtectedId Byte

- **bitIndex**: 
  - Starts disturbance at bit position `<bitIndex>`.
  - An index in the range 0-7 specifies a data bit, while the index 8 specifies the stop bit. Higher index values specify the interbyte-space after the indexed data byte. In which case, the user should make sure that the interbyte space is large enough.
  - Value range: 0..255

- **disturbanceHeaderID**: 
  - Frame ID to be used for the header disturbance.
  - **Note**: This is not the ID of the header to be disturbed, but the ID of the header disturbance itself.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linDisturbRespWithHeader](CAPLfunctionLINDisturbRespWithHeader.md) • [linDisturbHeaderWithBitStream](CAPLfunctionLINDisturbHeaderWithBitStream.md) • [linDisturbRespWithBitStream](CAPLfunctionLINDisturbRespWithBitStream.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)