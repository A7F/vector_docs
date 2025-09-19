[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysEndVariableStructUpdate.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysEndVariableStructUpdate

# sysEndVariableStructUpdate

**Valid for**: [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysEndVariableStructUpdate(char namespace[], char variable[]); // form 1`
- `long sysEndVariableStructUpdate(sysvarName); // form 2`

## Description

Ends the update of several elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md).

Use this function and the corresponding [sysBeginVariableStructUpdate](CAPLfunctionSysBeginVariableStructUpdate.md) to change several elements at the same time without the variable having an intermediate value where only some elements are changed.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable. SysVarName: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: no error, function successful
- **-1**: variable was not found

## Example

```plaintext
sysEndVariableStructUpdate(sysvar::XCP::ECU_2::KL2);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
