[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINDisturbHeaderWithVariableBitStream.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linDisturbHeaderWithVariableBitStream

# linDisturbHeaderWithVariableBitStream

Valid for: CANoe DE

## Function Syntax

```
dword linDisturbHeaderWithVariableBitStream(dword byteIndex, dword bitIndex, byte dataBuffer[], int64 lengthInNS[], dword numberOfBits, dword roundUp, dword timeoutPrevention);
```

## Description

Configures the LIN hardware to disturb the next header with a variable bitstream.

## Parameters

- **byteIndex**  
  Start disturbance in byte with index `<byteIndex>`.
  - 0: Sync Byte
  - 1: ProtectedId Byte

- **bitIndex**  
  The index of the bit where the interrupting bitstream will start. An index in the range 0-7 specifies a data bit, while the index 8 specifies the stop bit. Higher index values specify the interbyte-space after the indexed data byte. In which case, the user should make sure that the interbyte space is large enough.  
  Value range: 0..255

- **bitStream**  
  The bitstream to be used for the interruption.  
  Maximum number of bits: 2^31-1.

- **lengthInNS**  
  The length of each bit in nanoseconds.

- **numberOfBits**  
  The number of bits in the bitStream-array. Note that while the dataBuffer-array will usually have a size of ceil (numberOfBits / 8), the size of **lengthInNS** will need to be at least **numberOfBits**.

- **roundup**  
  If true, the lengths specified in **lengthInNS** will be rounded up to the next possible length that can be transmitted by the LIN hardware, otherwise the lengths will be rounded down.

- **timeoutPrevention**  
  - 0: deactivates the timeout prevention for the 7259- or 7269-transceiver.
  - 1: activates the timeout prevention for the 7259- or 7269-transceiver.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linDisturbHeaderWithHeader](CAPLfunctionLINDisturbHeaderWithHeader.md) • [linDisturbRespWithHeader](CAPLfunctionLINDisturbRespWithHeader.md) • [linDisturbHeaderWithBitStream](CAPLfunctionLINDisturbHeaderWithBitStream.md) • [linDisturbRespWithBitStream](CAPLfunctionLINDisturbRespWithBitStream.md) • [linDisturbRespWithVariableBitStream](CAPLfunctionLINDisturbRespWithVariableBitStream.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
