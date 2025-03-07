[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysDefineVariableData.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysDefineVariableData

# sysDefineVariableData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
Variables defined with this function can only be accessed using the `sysGetVariable.../sysSetVariable...` functions where namespace and variable name are given as string parameters. The variable can only be created with an available namespace. The namespace can be created with [sysDefineNamespace](CAPLfunctionSysDefineNameSpace.md).

## Function Syntax

```plaintext
long sysDefineVariableData(char namespace[], char variable[], byte initialData[], long initialSize);
```

## Description

Defines a variable of data type.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **initialData**: Initial value of the variable.
- **initialSize**: Initial size (in bytes) of the variable. Must not exceed the length of the initialData array.

## Return Values

- **0**: no error, function successful
- **1**: namespace was not found or second try to define the same namespace
- **2**: variable was not found or second try to define the same variable
- **3**: no writing right for the namespace available
- **4**: the variable has no suitable type for the function

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)