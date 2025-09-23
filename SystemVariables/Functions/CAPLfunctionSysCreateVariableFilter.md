[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysCreateVariableFilter.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysCreateVariableFilter

# sysCreateVariableFilter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long sysCreateVariableFilter(long filterType); // form 1
long sysCreateVariableFilter(long filterType, char filterName[]); // form 2
```

## Description

Creates a new variable filter behind the node calling the function. If no **filterName** is given, the default filter with an empty name is created.

## Parameters

- **filterType**: Specifies the filter behavior:
  - 0: Stop Filter. Stops all variables that are added to it.
  - 1: Pass Filter. Stops all variables that are not added to it.

- **filterName**: The name of the new filter. The name is used to identify the filter later, when variables or namespaces are added.

  **Note**: An empty **filterName** refers to the default filter and can be omitted completely.

## Return Values

- **0**: No error, function successful.
- **1**: The filter type is not valid. The filter cannot be created.
- **4**: A filter with the given name already exists. The filter cannot be created. Note: if no name or an empty name was given, this return value means that the default filter already exists. It cannot be created a second time.

## Example

```plaintext
long result;
//create the default filter as a Stop Filter.
result = sysCreateVariableFilter(0);
```

[sysFilterAddNamespace](CAPLfunctionSysFilterAddNamespace.md) • [sysFilterAddVariable](CAPLfunctionSysFilterAddVariable.md) • [sysFilterRemoveNamespace](CAPLfunctionSysFilterRemoveNamespace.md) • [sysFilterRemoveVariable](CAPLfunctionSysFilterRemoveVariable.md) • [sysSetVariableFilterActive](CAPLfunctionSysSetVariableFilterActive.md)
