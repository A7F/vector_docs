[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysResetValue.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysResetValue

# sysResetValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long sysResetValue(sysvar * variable);
```

## Description

Resets a system variable to its initial value.

## Parameters

- **variable**: Name of the variable.

## Return Values

- **0**: Success
- **1**: The system variable has no initial value assigned or is only used for analysis purposes
- **-1**: Parameter is invalid (e.g. failure return from [lookupSysVar](../../Other/Functions/CAPLfunctionlookupSysvar.md))

## Example

—

[sysResetValues](CAPLfunctionSysResetValues.md) • [testResetSysVarValue](../../Test/Functions/CAPLfunctionTestResetSysVarValue.md)
