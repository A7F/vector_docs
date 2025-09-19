[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetVariableFilterActive.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysSetVariableFilterActive

# sysSetVariableFilterActive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long sysSetVariableFilterActive(dword active); // form 1
long sysSetVariableFilterActive(dword active, char filterName[]); // form 2
```

## Description

Activates or deactivates a variable filter. If no **filterName** is given, the default filter is affected.

## Parameters

- **active**: Specifies the new filter status:
  - 0: deactivated.
  - All other values: activated.

- **filterName**: The name of the filter that should be affected.

  **Note**: An empty **filterName** refers to the default filter and can be omitted completely.

## Return Values

- **0**: No error, function successful.
- **2**: The filter does not exist. The filter status cannot be changed.

## Example

```plaintext
long result;
//create the default filter as a Stop Filter.
result = sysCreateVariableFilter(0);
//deactivate the default filter.
result = sysSetVariableFilterActive(0);
```

[SysCreateVariableFilter](CAPLfunctionSysCreateVariableFilter.md) • [SysFilterAddNamespace](CAPLfunctionSysFilterAddNamespace.md) • [SysFilterAddVariable](CAPLfunctionSysFilterAddVariable.md) • [SysFilterRemoveNamespace](CAPLfunctionSysFilterRemoveNamespace.md) • [SysFilterRemoveVariable](CAPLfunctionSysFilterRemoveVariable.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
