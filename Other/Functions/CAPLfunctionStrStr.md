[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrStr.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » strstr, strstr_off

# strstr, strstr_off

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long strstr(char s1[], char s2[]);
long strstr_off(char s1[], long offset, char s2[]);
```

## Description

Searches in **s1** for **s2**.

**Note**: A character may need several bytes depending on the string encoding, e.g., Japanese characters in Windows ANSI (932) encoding or any special characters in UTF-8 encoding. In that case, you should use [mbstrstr](CAPLfunctionMbStrStr.md)/[mbstrstr_off](CAPLfunctionMbStrStr.md) instead.

## Parameters

- **s1**: First string
- **offset**: Offset in s1 in bytes at which the search shall be started
- **s2**: Second string

## Return Values

First position in bytes of **s2** in **s1**, or -1 if **s2** is not found in **s1**.

## Example

```c
long pos;
char s1[18] = "Vector Informatik";
char s2[11] = "Informatik";
pos = strstr(s1, s2); // pos = 7
```

[strlen](CAPLfunctionStrLen.md) • [strncat](CAPLfunctionStrnCat.md) • [strncpy](CAPLfunctionStrnCpy.md) • [String Literal](../CAPLfunctionsStringLiteral.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)