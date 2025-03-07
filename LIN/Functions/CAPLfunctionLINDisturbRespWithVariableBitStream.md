[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINDisturbRespWithVariableBitStream.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linDisturbRespWithVariableBitStream

# linDisturbRespWithVariableBitStream

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linDisturbRespWithVariableBitStream(long disturbedFrameId, dword byteIndex, dword bitIndex, byte bitStream[], dword numberOfBits, dword timeoutPrevention);
```

## Description

Configures the LIN hardware to disturb the specified response with a variable bitstream.

## Parameters

- **disturbedFrameID**: ID of the bus event to be disturbed.  
  Value range: 0..63

- **byteIndex**: The index of the byte to be disturbed (use 0 for the first byte).  
  If the index is equal to the frame’s length, then the checksum byte will be disturbed. An index larger than the frame length is invalid.  
  Value range: 0..N, where N is frame length

- **bitIndex**: The index of the bit where the interrupting bitstream will start.  
  An index in the range 0-7 specifies a data bit, while the index 8 specifies the stop bit. Higher index values specify the interbyte-space after the indexed data byte. In which case, the user should make sure that the interbyte space is large enough.  
  Value range: 0..255

- **bitStream**: The bitstream to be used for the interruption.  
  Maximum number of bits: 2^31-1.

- **lengthInNS**: The length of each bit in nanoseconds.

- **umberOfBits**: The number of bits in the bitStream-array. Note that while the dataBuffer-array will usually have a size of ceil (numberOfBits / 8), the size of **lengthInNS** will need to be at least **numberOfBits**.

- **roundup**: If true, the lengths specified in **lengthInNS** will be rounded up to the next possible length that can be transmitted by the LIN hardware, otherwise the lengths will be rounded down.

- **timeoutPrevention**: 
  - 0: deactivates the timeout prevention for the 7259- or 7269-transceiver.
  - 1: activates the timeout prevention for the 7259- or 7269-transceiver.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linDisturbHeaderWithHeader](CAPLfunctionLINDisturbHeaderWithHeader.md) • [linDisturbRespWithHeader](CAPLfunctionLINDisturbRespWithHeader.md) • [linDisturbHeaderWithBitStream](CAPLfunctionLINDisturbHeaderWithBitStream.md) • [linDisturbRespWithBitStream](CAPLfunctionLINDisturbRespWithBitStream.md) • [linDisturbHeaderWithVariableBitStream](CAPLfunctionLINDisturbHeaderWithVariableBitStream.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)