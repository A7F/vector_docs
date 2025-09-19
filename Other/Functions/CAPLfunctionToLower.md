[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionToLower.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » toLower

# toLower

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
char toLower(char c); // form 1
void toLower(char dest[], char source[], dword bufferSize); // form 2
```

## Description

Transforms a character or string to lower case. Only characters a-z and A-Z are supported.

## Parameters

- **c**: Character to be transformed.
- **source**: String to be transformed.
- **dest**: Destination buffer for the transformed string.
- **bufferSize**: Size of the destination buffer.

## Return Values

Lower case of the character (form 1).

## Example

```plaintext
char buffer[20];
toLower(buffer, "Vector", elcount(buffer)); // buffer contains "vector"
```

[toUpper](CAPLfunctionToUpper.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
