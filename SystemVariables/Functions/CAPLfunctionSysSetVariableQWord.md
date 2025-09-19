[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetVariableQWord.md)

CAPL Functions » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysSetVariableQWord

# sysSetVariableQWord

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysSetVariableQWord(char namespace[], char variable[], qword value); // form 1`
- `long sysSetVariableQWord(SysVarName, qword value); // form 2`

## Description

Sets the value of a variable of type unsigned 64bit integer.

**Note**

- [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md).
- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by `sysvarMember::` instead of `sysvar::`.

  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **value**: Receives the current value of the variable.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: no error, function successful
- **1**: namespace was not found
- **2**: variable was not found
- **4**: the variable has no suitable type for the function

## Example

```c
sysSetVariableQWord(sysvar::MyNamespace::UInt64Var, 1);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
