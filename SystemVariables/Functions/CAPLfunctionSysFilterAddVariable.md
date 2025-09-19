# sysFilterAddVariable

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysFilterAddVariable.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysFilterAddVariable

## Function Syntax

- `long sysFilterAddVariable(sysVar variable); // form 1`
- `long sysFilterAddVariable(sysVar variable, char filterName[]); // form 2`
- `long sysFilterAddVariable(char namespace[], char variable[]); // form 3`
- `long sysFilterAddVariable(char namespace[], char variable[], char filterName[]); // form 4`

## Description

Adds a variable to a filter. If no **filterName** is given, the variable will be added to the default filter.

## Parameters

- **variable**: The variable to add.
  - **Note**: If a struct member is specified, the whole struct will be added.

- **filterName**: The name of the filter the variable should be added to.
  - **Note**: An empty **filterName** refers to the default filter and can be omitted completely.

- **namespace**: The namespace that contains the variable.

- **variable (char[])**: The name of the variable.

## Return Values

- **0**: No error, function successful.
- **2**: The variable filter does not exist. The variable cannot be added.
- **3**: The variable is already added to the filter.
- **6**: The variable does not exist. The variable cannot be added.

## Example

```c
long result;
//create default filter as Stop Filter
result = sysCreateVariableFilter(0);
//add a variable that should be stopped by the filter
result = sysFilterAddVariable(sysvar::myNamespace::myVariable);
```

## Related Links

- [sysCreateVariableFilter](CAPLfunctionSysCreateVariableFilter.md)
- [sysFilterAddNamespace](CAPLfunctionSysFilterAddNamespace.md)
- [sysFilterRemoveNamespace](CAPLfunctionSysFilterRemoveNamespace.md)
- [sysFilterRemoveVariable](CAPLfunctionSysFilterRemoveVariable.md)
- [sysSetVariableFilterActive](CAPLfunctionSysSetVariableFilterActive.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
