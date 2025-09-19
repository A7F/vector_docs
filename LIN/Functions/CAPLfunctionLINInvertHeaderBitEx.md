# linInvertHeaderBitEx

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINInvertHeaderBitEx.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linInvertHeaderBitEx

**Valid for**: CANoe DE

## Function Syntax

- `dword linInvertHeaderBitEx(dword byteIndex, dword bitIndex, dword bitOffsetInSixteenthBits, dword distLengthInSixteenthBits, dword level); // form 1`
- `dword linInvertHeaderBitEx(dword byteIndex, dword bitIndex, dword bitOffsetInSixteenthBits, dword distLengthInSixteenthBits, dword level, dword numberOfExecutions, dword reportFallingEdges); // form 2`
- `dword linInvertHeaderBitEx(dword byteIndex, dword bitIndex, dword bitOffsetInSixteenthBits, dword distLengthInSixteenthBits, dword level, dword numberOfExecutions, dword reportFallingEdges, long disturbAfterHeaderID, dword waitForHeaders); // form 3`

## Description

Inverts the specified number of 1/16`<sup>`th`</sup>` bits at the specified position in the next LIN header.

**Note**: Partial bit disturbances require the activation of the flash mode in order to get the edges of the disturbance fast enough. Call [linActivateFlashMode](CAPLfunctionLINActivateFlashMode.md) for that purpose.

## Parameters

- **byteIndex**: Index of the byte.
  - `-1`: Sync Break
  - `0`: Sync Byte
  - `1`: ProtectedId Byte

- **bitIndex**: The index of the bit to be manipulated.
  - Value range: 0..255

- **bitOffsetInSixteenthBits**: The offset in 1/16`<sup>`th`</sup>` bits into the bit specified in `bitIndex`.
  - Value range: 0..15

- **distLengthInSixteenthBits**: The length of the disturbance in units of 1/16`<sup>`th`</sup>` bit.
  - Value range: 0..65535

- **Level**: Level of the disturbance.
  - `0`: Dominant (inverts recessive bit)
  - `1`: Recessive (inverts dominant bit – requires mag-Cab/Piggyback and external power supply)

- **numberOfExecutions**: The number of consecutive headers in which the bit inversion will be executed.
  - Default: 1 (single shot). The largest possible value is 255.

- **reportFallingEdges**: Flag indicating whether time stamps of the falling edges in the resulting pseudo-byte have to be reported.

- **disturbAfterHeaderID**: With this parameter and the next one it is possible to define exactly which header will be disturbed.

- **waitForHeaders**: See explanation for `disturbAfterHeaderID`.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
on key 'i'
{
   if (0!=linInvertHeaderBitEx(0, 0, 8, 8, 0))
   {
      // for the next LIN header invert the second half of the first bit (it’s the recessive one) of the Sync byte
   }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
