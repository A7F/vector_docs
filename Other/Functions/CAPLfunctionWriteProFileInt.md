[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteProFileInt.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeProfileInt

# writeProfileInt

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**

Before this function can be called the write [path](../CAPLfunctionsFileSearchProcedure.md) must be set by the function [setWritePath](CAPLfunctionSetWritePath.md). Otherwise the configuration directory will be used. A relative filename must be passed to the function.

## Function Syntax

```plaintext
long writeProfileInt(char section[], char entry[], long value, char filename[]); // form 1
long writeProfileInt(char section[], char entry[], long value, char filename[], dword utf16); // form 2
```

## Description

Opens the file **filename**, searches the **section** section and writes the variable **entry** with the **value** value. If **entry** already exists the old **value** is overwritten.

`WriteProfileInt` always writes passed values in hexadecimal with prefix **0x** to a file.

## Parameters

- **section**: Section of the file as a string.
- **entry**: Variable name as a string.
- **value**: Value as an integer.
- **filename**: File path as a string.
- **utf16**: If this flag is set the file will be UTF-16LE encoded if it is newly written, or interpreted as such, if the corresponding BOM is also present.

## Return Values

The functional result is 0 in case of an error.

## Example

See [WriteProfileInt](CAPLfunctionsExampleProfile.md)
