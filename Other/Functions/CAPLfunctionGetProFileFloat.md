[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetProFileFloat.md)

## getProfileFloat

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getProfileFloat

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Note
A filename must be passed to this function. The absolute filename is determined by means of a [search procedure](../CAPLfunctionsFileSearchProcedure.md).

### Function Syntax

```plaintext
float getProfileFloat(char section[], char entry[], long def, char filename[]); // form 1
float getProfileFloat(char section[], char entry[], long def, char filename[], dword utf16); // form 2
```

### Description
Searches the file **filename** under section **section** for the variable **entry**. If its value is a number, this number is returned as the functional result. If the file or entry is not found, the default value def is returned as the functional result. If the entry does not contain a valid number, positive zero is returned. If the value is out of range for float, positive infinity is returned instead.

### Parameters
- **section**: Section of the file as a string.
- **entry**: Variable name as a string.
- **def**: Default value in case of error as a float.
- **filename**: File path as a string.
- **utf16**: If this flag is set the file will be interpreted as UTF-16LE encoded, if the corresponding BOM is also present.

### Return Values
Float that was read in.

### Example
See [getProfileFloat](CAPLfunctionsExampleProfile.md)
