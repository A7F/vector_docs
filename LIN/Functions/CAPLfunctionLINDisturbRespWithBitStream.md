[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINDisturbRespWithBitStream.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linDisturbRespWithBitStream

# linDisturbRespWithBitStream

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linDisturbRespWithBitStream(long disturbedFrameId, dword byteIndex, dword bitIndex, byte bitStream[], dword numberOfBits, dword timeoutPrevention);
```

## Description

Configures the LIN hardware to disturb the specified response with a bitstream.

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

- **numberOfBits**: The number of bits in the bitStream-array.

- **timeoutPrevention**:  
  0: deactivates the timeout prevention for the 7259- or 7269-transceiver.  
  1: activates the timeout prevention for the 7259- or 7269-transceiver.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linDisturbHeaderWithHeader](CAPLfunctionLINDisturbHeaderWithHeader.md) • [linDisturbRespWithHeader](CAPLfunctionLINDisturbRespWithHeader.md) • [linDisturbHeaderWithBitStream](CAPLfunctionLINDisturbHeaderWithBitStream.md) • [linDisturbHeaderWithVariableBitStream](CAPLfunctionLINDisturbHeaderWithVariableBitStream.md) • [linDisturbRespWithVariableBitStream](CAPLfunctionLINDisturbRespWithVariableBitStream.md)
