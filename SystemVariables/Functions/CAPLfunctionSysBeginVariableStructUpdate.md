[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysBeginVariableStructUpdate.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysBeginVariableStructUpdate

# sysBeginVariableStructUpdate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysBeginVariableStructUpdate(char namespace[], char variable[]); // form 1`
- `long sysBeginVariableStructUpdate(sysvarName); // form 2`

## Description

Starts the update of several elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md).

Use this function and the corresponding [sysEndVariableStructUpdate](CAPLfunctionSysEndVariableStructUpdate.md) to change several elements at the same time without the variable having an intermediate value where only some elements are changed. Each call must be followed by a call to **sysEndVariableStructUpdate**, else the variable value will not change.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable. SysVarName: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: no error, function successful
- **-1**: variable was not found

## Example

```plaintext
sysBeginVariableStructUpdate(sysvar::XCP::ECU_2::KL2);
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
