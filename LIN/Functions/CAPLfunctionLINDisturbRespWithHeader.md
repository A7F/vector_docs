[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINDisturbRespWithHeader.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linDisturbRespWithHeader

# linDisturbRespWithHeader

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
dword linDisturbRespWithHeader(long disturbedFrameId, dword byteIndex, dword bitIndex, long disturbingFrameId);
```

## Description

Configures the LIN hardware to disturb the specified response with a new header (id=`<disturbanceHeaderID>`).

## Parameters

- **disturbedFrameID**: ID of the bus event to be disturbed.  
  Value range: 0..63

- **byteIndex**: The index of the byte to be disturbed (use 0 for the first byte).  
  If the index is equal to the frame’s length, then the checksum byte will be disturbed. An index larger than the frame length is invalid.  
  Value range: 0..N, where N is frame length

- **bitIndex**: The index of the bit where the interrupting header will start.  
  An index in the range 0-7 specifies a data bit, while the index 8 specifies the stop bit. Higher index values specify the interbyte-space after the indexed data byte. In which case, the user should make sure that the interbyte space is large enough.  
  Value range: 0..255

- **disturbingFrameId**: The identifier of the header that will interrupt the specified header byte.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linDisturbHeaderWithHeader](CAPLfunctionLINDisturbHeaderWithHeader.md) • [linDisturbHeaderWithBitStream](CAPLfunctionLINDisturbHeaderWithBitStream.md) • [linDisturbRespWithBitStream](CAPLfunctionLINDisturbRespWithBitStream.md) • [linDisturbHeaderWithVariableBitStream](CAPLfunctionLINDisturbHeaderWithVariableBitStream.md) • [linDisturbRespWithVariableBitStream](CAPLfunctionLINDisturbRespWithVariableBitStream.md)
