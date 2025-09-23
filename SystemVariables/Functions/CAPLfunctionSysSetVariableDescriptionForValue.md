[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetVariableDescriptionForValue.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysSetVariableDescriptionForValue

# sysSetVariableDescriptionForValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long sysSetVariableDescriptionForValue(char namespace[], char variable[], long value, char description[]);
```

## Description

Sets a description for a particular value of a system variable of type Integer or Integer Array.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **value**: Value for which the description shall be set.
- **description**: New description for the value.

## Return Values

- **0**: no error, function successful
- **2**: variable was not found or second try to define the same variable

## Example

```plaintext
sysSetVariableDescriptionForValue("Dynamic", "IntVar", 0, "Zero");
```
