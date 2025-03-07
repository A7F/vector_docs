[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysDefineVariableLong.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysDefineVariableLong

# sysDefineVariableLong

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**

Variables defined with this function can only be accessed using the `sysGetVariable.../sysSetVariable...` functions where namespace and variable name are given as string parameters. The variable can only be created with an available namespace. The namespace can be created with [sysDefineNamespace](CAPLfunctionSysDefineNameSpace.md).

## Function Syntax

```plaintext
long sysDefineVariableLong(char namespace[], char variable[], long initialValue); // form 1
long sysDefineVariableLong(char namespace[], char variable[], long initialValue, long minimum, long maximum); // form 2
```

## Description

Defines a variable of the long type.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **initialValue**: Initial value of the variable.
- **minimum**: The minimum value of the variable.
- **maximum**: The maximum value of the variable.

## Return Values

- **0**: no error, function successful
- **1**: namespace was not found or second try to define the same namespace
- **2**: variable was not found or second try to define the same variable
- **3**: no writing right for the namespace available
- **4**: the variable has no suitable type for the function
- **5**: given minimum is larger than the given maximum

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)