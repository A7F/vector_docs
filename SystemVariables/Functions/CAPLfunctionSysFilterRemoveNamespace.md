[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysFilterRemoveNamespace.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysFilterRemoveNamespace

# sysFilterRemoveNamespace

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysFilterRemoveNamespace(char namespace[]); // form 1`
- `long sysFilterRemoveNamespace(char namespace[], char filterName[]); // form 2`

## Description

Removes a namespace from the variable filter. If no **filterName** is given, the namespace is removed from the default filter.

## Parameters

- **namespace**: The namespace to remove.
- **filterName**: The name of the filter the namespace should be removed from.

  **Note**: An empty **filterName** refers to the default filter and can be omitted completely.

## Return Values

- **0**: No error, function successful.
- **2**: The variable filter does not exist. The namespace cannot be removed.
- **3**: The namespace is not filtered by the filter. The namespace cannot be removed.

## Example

```c
long result;
// remove a namespace from the default filter.
result = sysFilterRemoveNamespace("myNamespace");
```

[sysCreateVariableFilter](CAPLfunctionSysCreateVariableFilter.md) • [sysFilterAddNamespace](CAPLfunctionSysFilterAddNamespace.md) • [sysFilterAddVariable](CAPLfunctionSysFilterAddVariable.md) • [sysFilterRemoveVariable](CAPLfunctionSysFilterRemoveVariable.md) • [sysSetVariableFilterActive](CAPLfunctionSysSetVariableFilterActive.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)