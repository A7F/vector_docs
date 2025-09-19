[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMbStrStr.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » mbstrstr, mbstrstr_off

# mbstrstr, mbstrstr_off

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long mbstrstr(char s1[], char s2[]);
long mbstrstr_off(char s1[], long offset, char s2[]);
```

## Description

Searches in **s1** for **s2**.

## Parameters

- **s1**: First string
- **s2**: Second string
- **offset**: Offset in s1 in **characters** at which the search shall be started

## Return Values

First position in characters of **s2** in **s1**, or -1 if **s2** is not found in **s1**.

## Example

```plaintext
long pos;
char s[50] = "'Tür' is german for 'door'";
pos = mbstrstr(s, "german");
write("%d", pos); // 9
```

[strstr](CAPLfunctionStrStr.md) • [mbstrlen](CAPLfunctionMbStrLen.md) • [mbstrncpy](CAPLfunctionMbStrnCpy.md) • [strncat](CAPLfunctionStrnCat.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
