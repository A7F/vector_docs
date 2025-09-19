[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrLen.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » strlen

# strlen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long strlen(char s[]);
```

## Description

The functional result is the length of the string **s** in **bytes**.

**Note**: A character may need several bytes depending on the string encoding, e.g. Japanese characters in Windows ANSI (932) encoding or any special characters in UTF-8 encoding. In that case, you may want to use [mbstrlen](CAPLfunctionMbStrLen.md) instead.

## Parameters

**string**

## Return Values

Length of the string in bytes.

## Example

```plaintext
long length;
char buffer[100] = "CANalyzer";
length = strlen(buffer);
```

Result:

```
length = 9
```

[strncat](CAPLfunctionStrnCat.md) • [strncmp](CAPLfunctionStrnCmp.md) • [strncpy](CAPLfunctionStrnCpy.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
