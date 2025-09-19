[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetProFileInt.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getProfileInt

# getProfileInt

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
A filename must be passed to this function. The absolute filename is determined by means of a [search procedure](../CAPLfunctionsFileSearchProcedure.md).

## Function Syntax

```plaintext
long getProfileInt(char section[], char entry[], long def, char filename[]); // form 1
long getProfileInt(char section[], char entry[], long def, char filename[], dword utf16); // form 2
```

## Description

Searches the file **filename** under **section** for the variable **entry**. If its value is a number, this number is returned as the functional result. If the file or entry is not found, or if entry does not contain a valid number, the default value def is returned as the functional result.

## Parameters

- **section**: Section of the file as a string.
- **entry**: Variable name as a string.
- **def**: Default value in case of error as an integer.
- **filename**: File path as a string.
- **utf16**: If this flag is set the file will be interpreted as UTF-16LE encoded, if the corresponding BOM is also present.

## Return Values

Integer that was read in.

## Example

See [getProfileInt](CAPLfunctionsExampleProfile.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
