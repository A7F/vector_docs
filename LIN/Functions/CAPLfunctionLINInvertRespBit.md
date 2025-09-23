[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINInvertRespBit.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linInvertRespBit

# linInvertRespBit

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `dword linInvertRespBit (long frameID, dword byteIndex, dword bitIndex); // form 1`
- `dword linInvertRespBit (long frameID, dword byteIndex, dword bitIndex, dword level); // form 2`
- `word linInvertRespBit (long frameID, dword byteIndex, dword bitIndex, dword level, dword numberOfExecutions); // form 3`
- `dword linInvertRespBit (long frameID, dword byteIndex, dword bitIndex, dword level, dword numberOfExecutions, dword reportFallingEdges); // form 4`

## Description

This function inverts the specified bit when the next bus event for the specified ID occurs, provided that the bus event contains the specified data byte.

## Parameters

- **frameID**: ID of the bus event to be manipulated.  
  Value range: 0..63

- **byteIndex**: The index of the byte to be manipulated (use 0 for the first byte). If the index is equal to the frame’s length, then the checksum byte will be manipulated. An index larger than the frame length is invalid.  
  Value range: 0..N, where N is frame length

- **bitIndex**: The index of the bit to be manipulated. An index in the range 0-7 will manipulate a data bit, while the index 8 will manipulate the stop bit. Higher index values will cause the interbyte-space after the data byte to be manipulated. In this case, the user should make sure that the interbyte-space is large enough.  
  Value range: 0..255

- **level**: Level of the disturbance  
  - 0: Dominant (inverts recessive bit)
  - 1: Recessive (inverts dominant bit – requires mag-Cab/Piggyback and external power supply)

- **numberOfExecutions**: The number of consecutive frames with the specified identifier in which the bit inversion will be executed.  
  Default: 1 (single shot).  
  The largest possible value is 255. If a larger value is given, 255 will be used.

- **reportFallingEdges**: Flag indicating whether time stamps of the falling edges in the resulting pseudo-byte have to be reported. The time stamps can be retrieved by calling [linGetFallingEdgesOfDisturbedByte](CAPLfunctionLINGetFallingEdgesOfDisturbedByte.md).  
  - 0: Deactivate report
  - 1: Activate report

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

Invert response bits on keyboard event

```plaintext
on key 'i'
{
...
// Invert first bit of byte field 8 for LIN frame with ID=0x33
linInvertRespBit(0x33, 7, 0);
...
// Invert bit 7 of checksum byte field for LIN frame with ID=0x33
linInvertRespBit(0x33, 8, 6);
...
// Invert stop bit of byte field 8 for LIN frame with ID=0x33
linInvertRespBit(0x33, 7, 8);
...
}
```

[linInvertHeaderBit](CAPLfunctionLINInvertHeaderBit.md) • [linDeactivateBitInversion](CAPLfunctionLINDeactivateBitInversion.md)
