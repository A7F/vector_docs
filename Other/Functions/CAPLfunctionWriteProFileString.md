[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteProFileString.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeProfileString

# writeProfileString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
Before this function can be called the write [path](../CAPLfunctionsFileSearchProcedure.md) must be set by the function [setWritePath](CAPLfunctionSetWritePath.md). Otherwise the configuration directory will be used. A relative filename must be passed to the function.

## Function Syntax

```
long writeProfileString(char section[], char entry[], char value[], char filename[]); // form 1
long writeProfileString(char section[], char entry[], char value[], char filename[], dword utf16); // form 2
```

## Description

Opens the file **filename**, searches the **section** section and writes the variable **entry** with the **value** value. If **entry** already exists the old **value** is overwritten. The functional result is the number of characters written or 0 in case of an error.

## Parameters

- **section**: Section of the file as a string.
- **entry**: Variable name as a string.
- **value**: Value as a string.
- **filename**: File path as a string.
- **utf16**: If this flag is set the file will be UTF-16LE encoded if it is newly written, or interpreted as such, if the corresponding BOM is also present.

## Return Values

- **0**: Write error
- **> 1**: Write access. Number of characters will not be returned.

## Example

See [WriteProfileString](CAPLfunctionsExampleProfile.md)
