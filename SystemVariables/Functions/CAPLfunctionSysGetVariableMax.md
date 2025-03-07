# sysGetVariableMax

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableMax.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableMax

## Function Syntax

- `long sysGetVariableMax(SysVarName, long& maxValue); // form 1`
- `long sysGetVariableMax(SysVarName, double& maxValue); // form 2`
- `long sysGetVariableMax(char namespace[], char variable[], long& maxValue); // form 3`
- `long sysGetVariableMax(char namespace[], char variable[], double& maxValue); // form 4`
- `long sysGetVariableMax(SysVarName, dword& maxValue); // form 5`
- `long sysGetVariableMax(char namespace[], char variable[], dword& maxValue); // form 6`
- `long sysGetVariableMax(SysVarName, int64& maxValue); // form 7`
- `long sysGetVariableMax(char namespace[], char variable[], int64& maxValue); // form 8`
- `long sysGetVariableMax(SysVarName, qword& maxValue); // form 9`
- `long sysGetVariableMax(char namespace[], char variable[], qword& maxValue); // form 10`

## Description

Retrieves the maximum of a variable.

**Note:** The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember::** instead of **sysvar::**.  
**Example:** `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".
- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **maxValue**: Receives the maximum of the variable if no errors occur (reference parameter). Must be the correct type for the system variable.

## Return Values

- **0**: success
- **4**: variable is of the wrong type or has no maximum defined

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)