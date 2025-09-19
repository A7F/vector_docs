[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetVariableArraySize.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » SysSetVariableArraySize

# SysSetVariableArraySize

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysSetVariableArraySize(sysvar variable, dword newSize); // form 1`
- `long sysSetVariableArraySize(char namespace[], char variable[], dword newSize); // form 2`

## Description

Sets the current array size of a system variable which has a generic array data type.

**Note**

- This function can’t be used for system variables of type Data, IntArray or FloatArray. For type Data, the size is changed implicitly when a new value is set. For types IntArray and FloatArray, the size can’t be changed.
- Note: The function can also be used for specific elements of a system variable of type struct or generic array. For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by `sysvarMember::` instead of `sysvar::`.
  - **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **variable (form 1)**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".
- **namespace (form 2)**: Name of the namespace
- **variable (form 2)**: Name of the variable
- **arraySize (form 2)**: new size of the array

## Return Values

- **0**: no error
- **2**: variable not found
- **4**: variable is not of a generic array type, or the array type doesn’t allow changing the size, or the new size is smaller than the minimum or bigger than the maximum size of the array type.

## Example

—

[sysGetVariableData](CAPLfunctionSysGetVariableData.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
