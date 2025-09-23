[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINInvertMultipleRespBits.md)

## linInvertMultipleRespBits

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linInvertMultipleRespBits

### Function Syntax

- `dword linInvertMultipleRespBit(long frameID, dword byteIndices[], dword bitIndices[], dword numberOfDisturbedBits[], dword levels[], dword arrSize); // form 1`
- `dword linInvertMultipleRespBit(long frameID, dword byteIndices[], dword bitIndices[], dword numberOfDisturbedBits[], dword levels[], dword arrSize, dword numberOfExecutions); // form 2`

### Description

Inverts the multiple bits in specified locations in the next LIN header.

**Note:**

- Some driver versions only support inverting multiple (consecutive) bits in one position (arrSize == 1).
- Please note [hardware-related restrictions](../../../CANoeCANalyzer/FunctionBlocks/LINDisturbanceBlock/LINDisturbanceBlockRestrictions.md).

### Parameters

- **frameID**: ID of the bus event to be manipulated.  
  Value range: 0..63

- **byteIndices**: An array of the indices of the bytes to be manipulated (use 0 for the first byte). If an index is equal to the frame’s length, then the checksum byte will be manipulated. An index larger than the frame length is invalid.  
  Value range: 0..N, where N is frame length

- **bitIndices**: An array of the indices of the bits to be manipulated. An index in the range 0-7 will manipulate a data bit, while the index 8 will manipulate the stop bit. Higher index values will cause the interbyte-space after the data byte to be manipulated. In this case, the user should make sure that the interbyte-space is large enough.  
  Value range: 0..255

- **numberOfDisturbedBits**: An array specifying how many consecutive bits shall be inverted at the specified locations.

- **levels**: An array of the levels of the disturbance  
  0: Dominant (inverts recessive bit)  
  1: Recessive (inverts dominant bit – requires mag-Cab/Piggyback and external power supply)

- **arrSize**: The number of elements in the above arrays. This value should not be greater than the size of the smallest array.

- **numberOfExecutions**: The number of consecutive frames with the specified identifier in which the bit inversion will be executed.  
  Default: 1 (single shot).  
  The largest possible value is 255. If a larger value is given, 255 will be used.

### Return Values

On success, a value unequal to zero, otherwise zero.

### Example

```c
// Invert response bits on keyboard event
on key 'i'
{
    dword byteIndices[2] = { 1, 5 };
    dword bitIndices[2]  =  { 0, 1 };
    dword numberOfDisturbedBits[2] = { 1, 2 };
    dword levels[2] = { 0, 1 };
    ...
    // Invert first bit 0 of byte 1 to dominant and bits 1 and 2
    // (numberOfDisturbedBits[1] is 2) of byte 5 to recessive
    linInvertMultipleRespBits(0x33, byteIndices, bitIndices, numberOfDisturbedBits, levels, 2);
    ...
}
```

[linInvertMultipleHeaderBits](CAPLfunctionLINInvertMultipleHeaderBits.md) • [linInvertHeaderBit](CAPLfunctionLINInvertHeaderBit.md) • [linInvertRespBit](CAPLfunctionLINInvertRespBit.md) • [linDeactivateBitInversion](CAPLfunctionLINDeactivateBitInversion.md)
