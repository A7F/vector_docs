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
