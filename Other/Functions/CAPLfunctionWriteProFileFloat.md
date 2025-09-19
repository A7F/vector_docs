[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteProFileFloat.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeProfileFloat

# writeProfileFloat

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
Before this function can be called the write [path](../CAPLfunctionsFileSearchProcedure.md) must be set by the function [setWritePath](CAPLfunctionSetWritePath.md). Otherwise the configuration directory will be used. A relative filename must be passed to the function.

## Function Syntax

```plaintext
long writeProfileFloat(char section[], char entry[], float value, char filename[]); // form 1
long writeProfileFloat(char section[], char entry[], float value, char filename[], dword utf16); // form 2
```

## Description

Opens the file **filename**, searches the **section** section and writes the variable **entry** with the **value** value. If **entry** already exists the old **value** is overwritten.

## Parameters

- **section**: Section of the file as a string.
- **entry**: Variable name as a string.
- **value**: Value as a float.
- **filename**: File path as a string.
- **utf16**: If this flag is set the file will be UTF-16LE encoded if it is newly written, or interpreted as such, if the corresponding BOM is also present.

## Return Values

The functional result is **0** in case of an error.

## Example

See [WriteProfileFloat](CAPLfunctionsExampleProfile.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
