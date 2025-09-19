[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINInvertHeaderBit.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linInvertHeaderBit

# linInvertHeaderBit

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `dword linInvertHeaderBit(dword byteIndex, dword bitIndex); // form 1`
- `dword linInvertHeaderBit(dword byteIndex, dword bitIndex, dword level); // form 2`
- `dword linInvertHeaderBit(dword byteIndex, dword bitIndex, dword level, dword numberOfExecutions); // form 3`
- `dword linInvertHeaderBit(dword byteIndex, dword bitIndex, dword level, dword numberOfExecutions, dword reportFallingEdges); // form 4`
- `dword linInvertHeaderBit(dword byteIndex, dword bitIndex, dword level, dword numberOfExecutions, dword reportFallingEdges, long disturbAfterHeaderID, dword waitForHeaders); // form 5`

## Description

Inverts the specified bit in the next LIN header.

## Parameters

- **byteIndex**: Index of the byte.
  - `-1`: Sync Break
  - `0`: Sync Byte
  - `1`: ProtectedId Byte

- **bitIndex**: The index of the bit to be manipulated. An index in the range 0-7 will manipulate a data bit, while the index 8 will manipulate the stop bit. Higher index values will cause the interbyte-space after the data byte to be manipulated. Value range: 0..255

- **level**: Level of the disturbance
  - `0`: Dominant (inverts recessive bit)
  - `1`: Recessive (inverts dominant bit – requires mag-Cab/Piggyback and external power supply)
  - Note: The default level used for the first type of the function is 0!

- **numberOfExecutions**: The number of consecutive headers in which the bit inversion will be executed. Default: 1 (single shot). The largest possible value is 255.

- **reportFallingEdges**: Flag indicating whether time stamps of the falling edges in the resulting pseudo-byte have to be reported.
  - `0`: Deactivate report
  - `1`: Activate report

- **disturbAfterHeaderID**: With this parameter and the next one it is possible to define exactly which header will be disturbed. For example: To disturb the next header directly after a header with the ID=5, set the `disturbAfterHeaderID` parameter to 5 and the `waitForHeaders` to 0.

- **waitForHeaders**: See explanation for `disturbAfterHeaderID`.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
on key 'i'
{
    if (0!=linInvertHeaderBit(0, 0, 0))
    {
        // for the next LIN header invert first bit (it’s the recessive one) of the Sync byte
    }
}
```

[linInvertRespBit](CAPLfunctionLINInvertRespBit.md) • [linDeactivateBitInversion](CAPLfunctionLINDeactivateBitInversion.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
