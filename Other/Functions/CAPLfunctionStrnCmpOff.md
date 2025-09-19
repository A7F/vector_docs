[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrnCmpOff.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » strncmp_off

# strncmp_off

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long strncmp_off(char s1[], long s1offset, char s2[], long s2offset, long len);
```

## Description

This function compares **s1** with **s2** for a maximum of **len** bytes.

If they are identical the functional result is 0.  
If **s1** is less than **s2** the result is -1, else +1.  
Comparison starts in **s1** at **s1offset** and in **s2** at **s2offset**.

**Note**: A character may need several bytes depending on the string encoding, e.g. Japanese characters in Windows ANSI (932) encoding or any special characters in UTF-8 encoding. In that case, you should use [mbstrncmp_off](CAPLfunctionMbStrnCmp.md) instead.

## Parameters

- **s1**: First string
- **s2**: Second string
- **s1offset**: Offset in **s1** in bytes
- **s2offset**: Offset in **s2** in bytes
- **len**: Maximum number of bytes to compare

## Return Values

- **-1**: if s1 is less than s2
- **1**: if s2 is less than s1
- **0**: if the strings are equal

## Example

```c
char s1[18] = "Vector Informatik";
char s2[11] = "Informatik";
if (strncmp_off(s1, 7, s2, 0, strlen(s2)) == 0)
    write("Equal!");
else
    write("Unequal!");
```

[strlen](CAPLfunctionStrLen.md) • [strncat](CAPLfunctionStrnCat.md) • [strncpy](CAPLfunctionStrnCpy.md) • [strncmp](CAPLfunctionStrnCmp.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
