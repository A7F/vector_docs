[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionatoi64.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » _atoi64

# _atoi64

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
int64 _atoi64(char s[]);
```

## Description

Converts the string **s** to a 64bit integer. The number base is decimal.

## Parameters

- **s**: String to be converted.

## Return Values

- The converted number.
- The return value is 0 if the string can’t be converted to a number. It is the largest positive/negative number in case of overflow.

## Example

```plaintext
int64 i;
i = _atoi64("12345678901")
```

[strtoll](CAPLfunctionStrtoll.md) • [strtoull](CAPLfunctionStrtoull.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
