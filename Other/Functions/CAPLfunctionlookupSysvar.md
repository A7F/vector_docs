[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionlookupSysvar.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » lookupSysvar

# lookupSysvar

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `sysvar * lookupSysvar(char sysvarName[]); // form 1`
- `sysvar * lookupSysvar(char namespace[], char variable[]); // form 2`

## Description

Searches for a system variable definition. If the system variable is not found, test modules/units report an **error in test system** while simulation/analysis nodes write a warning into the Write Window, and the function returns an invalid `sysvar`.

**Notes**

It is recommended to use this function only in special cases or during measurement start, since searching for the database definition may impact realtime performance.

## Parameters

- **sysvarName**: Fully qualified name of the variable (including namespaces)
- **namespace**: Namespace(s) of the variable, separated with **::**
- **variable**: Name of the variable

## Return Values

The found system variable or an invalid object.

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
