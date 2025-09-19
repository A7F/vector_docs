[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysDefineVariableLongLong.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysDefineVariableLongLong

# sysDefineVariableLongLong

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**

Variables defined with this function can only be accessed using the `sysGetVariable.../sysSetVariable...` functions where namespace and variable name are given as string parameters. The variable can only be created with an available namespace. The namespace can be created with [sysDefineNamespace](CAPLfunctionSysDefineNameSpace.md).

## Function Syntax

```plaintext
long sysDefineVariableLongLong(char namespace[], char variable[], int64 initialValue);
```

## Description

Defines a variable of the Int64 type.

## Parameters

- **namespace**: name of the namespace
- **variable**: name of the variable
- **initialValue**: initial value of the variable

## Example

—

[sysDefineVariableLong](CAPLfunctionSysDefineVariableLong.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
