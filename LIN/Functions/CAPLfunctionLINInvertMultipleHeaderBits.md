[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINInvertMultipleHeaderBits.md)

**CAPL Functions** » **LIN** » **linInvertMultipleHeaderBits**

# linInvertMultipleHeaderBits

**Valid for**: CANoe DE

## Function Syntax

- `dword linInvertMultipleHeaderBits(dword byteIndices[],dword bitIndices[],dword numberOfDisturbedBits[],dword levels[],dword arrSize); // form 1`
- `dword linInvertMultipleHeaderBits(dword byteIndices[],dword bitIndices[],dword numberOfDisturbedBits[],dword levels[],dword arrSize, dword numberOfExecutions); // form 2`
- `dword linInvertMultipleHeaderBits(dword byteIndices[],dword bitIndices[],dword numberOfDisturbedBits[],dword levels[],dword arrSize, dword numberOfExecutions, long disturbAfterHeaderID, dword waitForHeaders); // form 3`

## Description

Inverts the multiple bits in specified locations in the next LIN header.

**Note**: Some driver versions only support inverting multiple (consecutive) bits in one position (arrSize == 1).

## Parameters

- **byteIndices**: An array of the index of the bytes.
  - `-1`: Sync Break
  - `0`: Sync Byte
  - `1`: ProtectedId Byte

- **bitIndices**: The index of the bit to be manipulated. An index in the range 0-7 will manipulate a data bit, while the index 8 will manipulate the stop bit. Higher index values will cause the interbyte-space after the data byte to be manipulated. In this case, the user should make sure that the interbyte-space is large enough. Value range: 0..255

- **numberOfDisturbedBits**: An array specifying how many consecutive bits shall be inverted at the specified locations.

- **level**: An array of the levels of the disturbance
  - `0`: Dominant (inverts recessive bit)
  - `1`: Recessive (inverts dominant bit – requires mag-Cab/Piggyback and external power supply)

- **arrSize**: The number of elements in the above arrays. This value should not be greater than the size of the smallest array.

- **numberOfExecutions**: The number of consecutive headers in which the bit inversion will be executed. Default: 1 (single shot). The largest possible value is 255. If a larger value is given, 255 will be used.

- **disturbAfterHeaderID**: With this parameter and the next one it is possible to define exactly which header will be disturbed. The LIN hardware will first wait for a header with ID = `disturbAfterHeaderID` before additionally awaiting the number of headers defined by `waitForHeaders`. The next header following these headers will then be disturbed.

- **waitForHeaders**: See explanation for `disturbAfterHeaderID`.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
on key 'i'
{
   dword byteIndices[2] = { 0, 1}; // invert in sync field and in id-byte
   dword bitIndices[2]  = { 0, 0 }; // invert the first data bits in each byte
   dword numberOfDisturbedBits[2] = { 1, 2 }; // invert 1 bit in sync field, 2 bits in id-byte
   dword levels[2] = { 0, 1 }; // push sync field bit to dominant, id-byte bits to recessive
   if (0!=linInvertMultipleHeaderBits(byteIndices, bitIndices, numberOfDisturbedBits, levels, 2))
   {
   }
}
```

[linInvertHeaderBit](CAPLfunctionLINInvertHeaderBit.md) • [linInvertRespBit](CAPLfunctionLINInvertRespBit.md) • [linDeactivateBitInversion](CAPLfunctionLINDeactivateBitInversion.md)
