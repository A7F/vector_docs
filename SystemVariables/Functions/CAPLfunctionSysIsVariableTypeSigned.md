[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysIsVariableTypeSigned.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysIsVariableTypeSigned

# sysIsVariableTypeSigned

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword sysIsVariableTypeSigned(sysvar * variable);
```

## Description

Returns whether the data type of the system variable is a signed numeric type. The function returns 1 for system variables of type Int64, Int32, Double, Integer Array and Double Array. It returns 0 for other variables, in particular for variables of type UInt32 and UInt64.

## Parameters

- **variable**: the variable

## Return Values

- **1**: if the variable has a signed numeric type
- **0**: otherwise

## Example

```c
sysvar * var;
var = lookupSysvar("SomeNamespace::SomeVariable");
write("Signed: %d", sysIsVariableTypeSigned(var));
```

[sysGetVariableSVType](CAPLfunctionsysGetVariableSVType.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
