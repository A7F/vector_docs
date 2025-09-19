[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableDescriptionForValue.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableDescriptionForValue

# sysGetVariableDescriptionForValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysGetVariableDescriptionForValue(SysVarName, long value, char buffer[], long bufferSize); // form 1`
- `long sysGetVariableDescriptionForValue(char namespace[], char variable[], long value, char buffer[], long bufferSize); // form 2`

## Description

Retrieves a description for a value of a system variable of type long or long array. In this way, you can access the value table of the system variable.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **value**: Value for which the description shall be retrieved.
- **buffer**: Buffer which receives the description.
- **bufferSize**: Size of the buffer.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: no error, function successful
- **2**: variable was not found or second try to define the same variable
- **5**: there is no description of this value for the variable
- **6**: the buffer is not large enough for the description

## Example

```c
char buffer[20];
sysGetVariableDescriptionForValue("Dynamic", "IntVar", 0, buffer, elcount(buffer));
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
