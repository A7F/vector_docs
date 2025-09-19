[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysDefineVariableFloatArray.md)

# sysDefineVariableFloatArray

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysDefineVariableFloatArray

**Valid for:** CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
Variables defined with this function can only be accessed using the `sysGetVariable.../sysSetVariable...` functions where namespace and variable name are given as string parameters. The variable can only be created with an available namespace. The namespace can be created with [sysDefineNamespace](CAPLfunctionSysDefineNameSpace.md).

## Function Syntax

```plaintext
long sysDefineVariableFloatArray(char namespace[], char variable[], float initialValues[], long arraySize); // form 1
long sysDefineVariableFloatArray(char namespace[], char variable[], double initialValues[], long arraySize, double minimum, double maximum); // form 2
```

## Description

Defines a variable of the float[] type.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **initialValue**: Initial value of the variable.
- **arraySize**: Number of values in the array.
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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
