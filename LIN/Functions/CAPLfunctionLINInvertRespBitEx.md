[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINInvertRespBitEx.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linInvertRespBitEx

# linInvertRespBitEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `dword linInvertRespBitEx(long frameID, dword byteIndex, dword bitIndex, dword bitOffsetInSixteenthBits, dword distLengthInSixteenthBits, dword level); // form 1`
- `dword linInvertRespBitEx(long frameID, dword byteIndex, dword bitIndex, dword bitOffsetInSixteenthBits, dword distLengthInSixteenthBits, dword level, dword numberOfExecutions, dword reportFallingEdges); // form 2`

## Description

Inverts the specified number of 1/16`<sup>`th</sup> bits at the specified position in the next LIN frame’s response with the specified frame ID.

**Note**: Partial bit disturbances require the activation of the flash mode in order to get the edges of the disturbance fast enough. Call [linActivateFlashMode](CAPLfunctionLINActivateFlashMode.md) for that purpose.

## Parameters

- **frameID**: ID of the bus event to be manipulated.  
  Value range: 0..63

- **byteIndex**: The index of the byte to be manipulated (use 0 for the first byte). If the index is equal to the frame’s length, then the checksum byte will be manipulated. An index larger than the frame length is invalid.  
  Value Range: 0..N: where N is the frame length

- **bitIndex**: The index of the bit to be manipulated. An index in the range 0-7 will manipulate a data bit, while the index 8 will manipulate the stop bit. Higher index values will cause the interbyte-space after the data byte to be manipulated. In this case, the user should make sure that the interbyte-space is large enough.  
  Value range: 0..255

- **bitOffsetInSixteenthBits**: The offset in 1/16`<sup>`th</sup> bits into the bit specified in **bitIndex**.  
  Value range: 0..15

- **distLengthInSixteenthBits**: The length of the disturbance in units of 1/16`<sup>`th</sup> bit.  
  Value range: 0..65535

- **Level**: Level of the disturbance.  
  - 0: Dominant (inverts recessive bit)
  - 1: Recessive (inverts dominant bit – requires mag-Cab/Piggyback and external power supply)

- **numberOfExecutions**: The number of consecutive frames with the specified identifier in which the bit inversion will be executed.  
  Default: 1 (single shot).  
  The largest possible value is 255. If a larger value is given, 255 will be used.

- **reportFallingEdges**: Flag indicating whether time stamps of the falling edges in the resulting pseudo-byte have to be reported. The time stamps can be retrieved by calling [linGetFallingEdgesOfDisturbedByte](CAPLfunctionLINGetFallingEdgesOfDisturbedByte.md).  
  0: Deactivate report

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
on key 'i'
{
   if (0!=linInvertRespBitEx(42, 1, 0, 8, 8, 0))
   {
      // in the next response of lin frame 42 invert the second half of the first bit of the first data byte (the bit has to be recessive)
   }
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
