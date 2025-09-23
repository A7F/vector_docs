[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableQWord.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableQWord

# sysGetVariableQWord

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `qword sysGetVariableQWord(char namespace[], char variable[]); // form 1`
- `qword sysGetVariableQWord(SysVarName); // form 2`
- `long sysGetVariableQWord(char namespace[], char variable[], qword& value); // form 3`
- `long sysGetVariableQWord(SysVarName, qword& value); // form 4`

## Description

Returns the value of a variable of type unsigned 64 bit integer.

**Note:**

- [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md).
- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by `sysvarMember::` instead of `sysvar::`.

  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **value**: Receives the current value of the variable.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **Value of the variable or 0 in case of error (form 1 and 2)**
- **0**: no error, function successful (form 3 and 4)
- **2**: variable was not found or second try to define the same variable (form 3 and 4)
- **4**: the variable has no suitable type for the function (form 3 and 4)

## Example

```plaintext
sysGetVariableQWord(sysvar::MyNamespace::UInt64Var);
```
