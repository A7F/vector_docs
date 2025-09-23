[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysFilterRemoveVariable.md)

**CAPL Functions** » **System Variables** » **sysFilterRemoveVariable**

# sysFilterRemoveVariable

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysFilterRemoveVariable(sysVar variable); // form 1`
- `long sysFilterRemoveVariable(sysVar variable, char filterName[]); // form 2`
- `long sysFilterRemoveVariable(char namespace[], char variable[]); // form 3`
- `long sysFilterRemoveVariable(char namespace[], char variable[], char filterName[]); // form 4`

## Description

Removes a variable from a variable filter. If no **filterName** is given, the variable will be removed from the default filter.

## Parameters

- **variable**: The variable to remove.
  - **Note**: If a struct member is specified, the whole struct will be removed.

- **filterName**: The name of the filter the variable should be removed from.
  - **Note**: An empty **filterName** refers to the default filter and can be omitted completely.

- **namespace**: The namespace that contains the variable.

- **variable (char[])**: The name of the variable.

## Return Values

- **0**: No error, function successful.
- **2**: The variable filter does not exist. The variable cannot be removed.
- **5**: The variable is not filtered by the filter. The variable cannot be removed.
- **6**: The variable does not exist. The variable cannot be removed.

## Example

```plaintext
long result;
//remove a variable from the default filter
result = sysFilterRemoveVariable(sysvar::myNamespace::myVariable);
```

[sysCreateVariableFilter](CAPLfunctionSysCreateVariableFilter.md) • [sysFilterAddNamespace](CAPLfunctionSysFilterAddNamespace.md) • [sysFilterAddVariable](CAPLfunctionSysFilterAddVariable.md) • [sysFilterRemoveNamespace](CAPLfunctionSysFilterRemoveNamespace.md) • [sysSetVariableFilterActive](CAPLfunctionSysSetVariableFilterActive.md)
