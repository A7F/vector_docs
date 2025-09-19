# mbstrncpy, mbstrncpy_off

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMbStrnCpy.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » mbstrncpy, mbstrncpy_off

## Function Syntax

```c
void mbstrncpy(char dest[], char src[], long len);
void mbstrncpy_off(char dest[], long destOffset, char src[], long len);
```

## Description

`mbstrncpy` function copies `src` to `dest`. `len` indicates the number of characters that shall be copied; use -1 to indicate that as much shall be copied into `dest` as will fit (maximum until the end of `src`). The function ensures that there is a terminating 0 byte; but in contrast to strncpy, that byte is not counted into `len`.

`mbstrncpy_off` overwrites characters in the destination buffer starting at the character offset `destOffset`.

## Parameters

- **dest**: Destination buffer
- **src**: Source string
- **len**: Number of characters to be copied, or -1 to copy as much as possible
- **destOffset**: Offset in characters into the destination buffer

## Return Values

—

## Example

```c
char s1[50] = "eine grüne "; // german for 'a green'
char s2[10] = "Türen"; // german for 'doors'
mbstrncpy_off(s1, 11, s2, 3);
write("%s", s1); // eine grüne Tür (german for 'a green door')
```

## Related Links

- [strncpy](CAPLfunctionStrnCpy.md)
- [mbstrlen](CAPLfunctionMbStrLen.md)
- [mbstrncmp](CAPLfunctionMbStrnCmp.md)
- [mbstrstr](CAPLfunctionMbStrStr.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
