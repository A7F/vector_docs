[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrnCmp.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » strncmp

# strncmp

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long strncmp(char s1[], char s2[], long len); // form 1
long strncmp(char s1[], char s2[], long s2offset, long len); // form 2
```

## Description

This function compares **s1** with **s2** for a maximum of **len** bytes. If they are identical the functional result is 0.  
If **s1** is less than **s2** the result is -1, else +1. Form 2 starts the comparison in **s2** at the specified offset.

**Note**: A character may need several bytes depending on the string encoding, e.g. Japanese characters in Windows ANSI (932) encoding or any special characters in UTF-8 encoding. In that case, you should use [mbstrncmp](CAPLfunctionMbStrnCmp.md) instead.

## Parameters

- **s1**: First string
- **s2**: Second string
- **s2offset**: Offset in **s2** in bytes
- **len**: Maximum number of bytes to compare

## Return Values

- **-1**: if s1 is less than s2
- **1**: if s2 is less than s1
- **0**: if the strings are equal

## Example

```plaintext
on key 's'
{
    char s1[7] = "Vector";
    char s2[7] = "Vector";
    if(strncmp(s1,s2,strlen(s1)))
        write("not equal");
    else
        write("equal");
}
```

[strlen](CAPLfunctionStrLen.md) • [strncat](CAPLfunctionStrnCat.md) • [strncpy](CAPLfunctionStrnCpy.md) • [strncmp_off](CAPLfunctionStrnCmpOff.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)