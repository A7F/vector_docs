[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINDisturbHeaderWithBitStream.md)

**CAPL Functions** » **LIN** » **linDisturbHeaderWithBitStream**

# linDisturbHeaderWithBitStream

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linDisturbHeaderWithBitStream(dword byteIndex, dword bitIndex, byte bitStream[], dword numberOfBits, dword timeoutPrevention);
```

## Description

Configures the LIN hardware to disturb the next header with a bitstream.

## Parameters

- **byteIndex**: Start disturbance in byte with index `<byteIndex>`.  
  - 0: Sync Byte  
  - 1: ProtectedId Byte

- **bitIndex**: The index of the bit where the interrupting bitstream will start.  
  An index in the range 0-7 specifies a data bit, while the index 8 specifies the stop bit. Higher index values specify the interbyte-space after the indexed data byte. In which case, the user should make sure that the interbyte space is large enough.  
  Value range: 0..255

- **bitStream**: The bitstream to be used for the interruption.  
  Maximum number of bits: 2^31-1.

- **numberOfBits**: The number of bits in the bitStream-array.

- **timeoutPrevention**:  
  - 0: deactivates the timeout prevention for the 7259- or 7269-transceiver.  
  - 1: activates the timeout prevention for the 7259- or 7269-transceiver.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linDisturbHeaderWithHeader](CAPLfunctionLINDisturbHeaderWithHeader.md) • [linDisturbRespWithHeader](CAPLfunctionLINDisturbRespWithHeader.md) • [linDisturbRespWithBitStream](CAPLfunctionLINDisturbRespWithBitStream.md) • [linDisturbHeaderWithVariableBitStream](CAPLfunctionLINDisturbHeaderWithVariableBitStream.md) • [linDisturbRespWithVariableBitStream](CAPLfunctionLINDisturbRespWithVariableBitStream.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
