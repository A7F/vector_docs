[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableValueForDescription.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableValueForDescription

# sysGetVariableValueForDescription

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long sysGetVariableValueForDescription(SysVarName, char description[], long& value); // form 1
long sysGetVariableValueForDescription(char namespace[], char variable[], char description[], long& value); // form 2
```

## Description

Retrieves the value for a value description of a system variable of type long or long array. In this way, you can access the value table of the system variable.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **description**: Description for which the value shall be retrieved.
- **value**: Receives the value for the description.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: no error, function successful
- **2**: variable was not found or second try to define the same variable
- **5**: there is no description of this value for the variable

## Example

```plaintext
long val;
sysGetVariableValueForDescription("Dynamic", "IntVar", "Zero", val);
```
