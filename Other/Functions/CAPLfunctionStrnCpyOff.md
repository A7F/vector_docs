[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrnCpyOff.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » strncpy_off

# strncpy_off

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
void strncpy_off(char dest[], long destOffset, char src[], long max);
```

## Description

This function copies **src** to **dest**. **max** indicates the size of **dest** in bytes.

The function ensures that there is a terminating '\0'. Thus, a maximum of max-1-destOffset bytes are copied. Bytes are overwritten in **dest** starting at **destOffset**.

**Note:** A character may need several bytes depending on the string encoding, e.g. Japanese characters in Windows ANSI (932) encoding or any special characters in UTF-8 encoding. In that case, you should use [mbstrncpy_off](CAPLfunctionMbStrnCpy.md) instead.

## Parameters

- **dest**: Destination buffer
- **destOffset**: Offset in destination buffer
- **src**: Source string
- **max**: Is used to determine the maximum number of copied bytes. Must not be larger than the size of **dest**. A maximum of max-1-destOffset bytes are copied. If **src** is shorter than that, bytes are only copied until a terminating '\0' is encountered.

## Return Values

—

## Example

```c
char s[6] = "Hello";
strncpy_off(s, 1, "e", elcount(s)); // s: He
```

[Related Functions: strlen](CAPLfunctionStrLen.md) • [strncat](CAPLfunctionStrnCat.md) • [strncmp](CAPLfunctionStrnCmp.md) • [strncpy](CAPLfunctionStrnCpy.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
