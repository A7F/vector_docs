[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMbStrnCmp.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » mbstrncmp, mbstrncmp_off

# mbstrncmp, mbstrncmp_off

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long mbstrncmp(char s1[], char s2[], long len);` // form 1
- `long mbstrncmp(char s1[], char s2[], long s2offset, long len);` // form 2
- `long mbstrncmp_off(char s1[], long s1offset, char s2[], long s2offset, long len);` // form 3

## Description

This function compares **s1** with **s2** for a maximum of **len** characters.

If they are identical the functional result is 0.  
If **s1** is less than **s2** the result is -1, else +1.

Comparison starts in **s1** at **s1offset** (form 3) and in **s2** at **s2offset** (form 2 and form 3).

## Parameters

- **s1**: First string
- **s2**: Second string
- **len**: Maximum number of characters to compare
- **s1offset**: Offset in **s1** in **characters**
- **s2offset**: Offset in **s2** in **characters**

## Return Values

- **-1**: if s1 is less than s2.
- **1**: if s2 is less than s1.
- **0**: if the strings are equal.

## Example

```c
char s[50] = "'Tür' is the german word for 'door'.";
write("%d", mbstrncmp_off(s, 13, "german", 0, 6)); // 0
```

[strncmp](CAPLfunctionStrnCmp.md) • [mbstrlen](CAPLfunctionMbStrLen.md) • [mbstrncpy](CAPLfunctionMbStrnCpy.md) • [mbstrstr](CAPLfunctionMbStrStr.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
