[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysFilterAddNamespace.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysFilterAddNamespace

# sysFilterAddNamespace

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long sysFilterAddNamespace(char namespace[]); // form 1
long sysFilterAddNamespace(char namespace[], char filterName[]); // form 2
```

## Description

Adds a namespace to the variable filter. If no **filterName** is given, the namespace is added to the default filter.

## Parameters

- **namespace**: The namespace to add. The existence of the namespace is not checked, and adding a namespace that is not defined is not an error. If the namespace gets defined after it is added to the filter, it is affected by the filter normally.

- **filterName**: The name of the filter the namespace should be added to.

  **Note**: An empty **filterName** refers to the default filter and can be omitted completely.

## Return Values

- **0**: No error, function successful.
- **2**: The variable filter does not exist. The namespace cannot be added.
- **3**: The variable is already added to the filter. The namespace cannot be added.

## Example

```plaintext
long result;
//create the default filter as a Stop Filter
result = sysCreateVariableFilter(0);
//add a namespace to the filter.
result = sysFilterAddNamespace("myNamespace");
```

[sysCreateVariableFilter](CAPLfunctionSysCreateVariableFilter.md) • [sysFilterAddVariable](CAPLfunctionSysFilterAddVariable.md) • [sysFilterRemoveNamespace](CAPLfunctionSysFilterRemoveNamespace.md) • [sysFilterRemoveVariable](CAPLfunctionSysFilterRemoveVariable.md) • [sysSetVariableFilterActive](CAPLfunctionSysSetVariableFilterActive.md)
