[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMbSubStrCpy.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » mbsubstr_cpy, mbsubstr_cpy_off

# mbsubstr_cpy, mbsubstr_cpy_off

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void mbsubstr_cpy(char dest[], char src[], long srcStart, long len);
void mbsubstr_cpy_off(char dest[], long destOffset, char src[], long srcStart, long len);
```

## Description

`mbsubstr_cpy` copies a substring of **src** to **dest**. **len** indicates the number of **characters** that shall be copied; use -1 to indicate that as much shall be copied into **dest** as will fit (maximum until the end of **src**). The function ensures that there is a terminating 0 byte; but in contrast to [substr_cpy](CAPLfunctionSubStrCpy.md)/[substr_cpy_off](CAPLfunctionSubStrCpyOff.md), that byte is not counted into **len**.

`mbsubstr_cpy_off` overwrites characters in the destination buffer starting at the **character** offset **destOffset**.

## Parameters

- **dest**: Destination buffer
- **src**: Source string
- **srcStart**: Start index in **characters** in **src** of substring
- **len**: Number of **characters** to be copied, or -1 to copy as much as possible
- **destOffset**: Offset in **characters** into the destination buffer

## Return Values

—

## Example

```plaintext
char s1[50] = "eine grüne "; // german for 'a green'
char s2[20] = "schöne Türen"; // german for 'beautiful doors'
mbsubstr_cpy_off(s1, 11, s2, 7, 3);
write("%s", s1); // eine grüne Tür (german for 'a green door')
```

[substr_cpy](CAPLfunctionSubStrCpy.md) • [substr_cpy_off](CAPLfunctionSubStrCpy.md) • [mbstrncpy](CAPLfunctionMbStrnCpy.md) • [mbstrlen](CAPLfunctionMbStrLen.md) • [mbstrncmp](CAPLfunctionMbStrnCmp.md) • [mbstrstr](CAPLfunctionMbStrStr.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)