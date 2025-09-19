[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableMin.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableMin

# sysGetVariableMin

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysGetVariableMin(SysVarName, long& minValue); // form 1`
- `long sysGetVariableMin(SysVarName, double& minValue); // form 2`
- `long sysGetVariableMin(char namespace[], char variable[], long& minValue); // form 3`
- `long sysGetVariableMin(char namespace[], char variable[], double& minValue); // form 4`
- `long sysGetVariableMin(SysVarName, dword& minValue); // form 5`
- `long sysGetVariableMin(char namespace[], char variable[], dword& minValue); // form 6`
- `long sysGetVariableMin(SysVarName, int64& minValue); // form 7`
- `long sysGetVariableMin(char namespace[], char variable[], int64& minValue); // form 8`
- `long sysGetVariableMin(SysVarName, qword& minValue); // form 9`
- `long sysGetVariableMin(char namespace[], char variable[], qword& minValue); // form 10`

## Description

Retrieves the minimum of a variable of type integer or integer array.

**Note**: The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember::** instead of **sysvar::**.
**Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".
- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **minValue**: Receives the minimum of the variable if no errors occur (reference parameter). Must be the correct type for the system variable.

## Return Values

- **0**: success
- **4**: variable is of the wrong type or has no minimum defined

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
