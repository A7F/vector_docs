[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSnPrintf.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » snprintf

# snprintf

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
long snprintf(char dest[], long len, char format[], ...);
```

## Description

This function corresponds to the C function `sprintf`. Supplementally, the parameter **len** indicates the maximum length of the array **dest**. The format string has the same meaning as with the function [write](CAPLfunctionWrite.md) and is described there.

**Note:** CAPL supports a function call with maximum 64 parameters.

## Parameters

- **dest**: Character buffer to print to.
- **len**: Maximum number of characters printed to buffer including terminating '\0'. Must be at most the size of the buffer.
- **format**: Formatted string printed to buffer.

## Return Values

The number of characters written.

## Example

```c
char buffer[100], str[7] = "Vector";
long i;
i = snprintf(buffer, elcount(buffer), "String: %s\n", str);
write("Output:\n%s : Character count = %d\n", buffer, i);
```

[write](CAPLfunctionWrite.md) • [String Literal](../CAPLfunctionsStringLiteral.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
