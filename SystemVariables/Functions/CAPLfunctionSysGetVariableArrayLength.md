[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableArrayLength.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableArrayLength

# sysGetVariableArrayLength

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `dword sysGetVariableArrayLength(char namespace[], char variable[]); // form 1`
- `dword sysGetVariableArrayLength(SysVarName); // form 2`

## Description

Returns the length of the array of the system variable.

**Note**

- [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md). An access to the whole array is with this variant not possible.
- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember::** instead of **sysvar::**.

  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- For system variables of type data, returns the current size (in bytes) of the value.
- For system variables of type long or float array, returns the number of elements in the array.
- For system variables of type string, returns the length of the string, excluding the terminating 0 character.
- For system variables of type long or float, returns 1.

## Example

```c
// calculate the norm of a vector
dword length, i;
double element, sum, norm;
sum = 0.0;
length = sysGetVariableArrayLength(sysvar::MyVariables::MyVector);
for (i = 0; i < length; ++i) {
    element = @sysvar::MyVariables::MyVector[i];
    sum += element * element;
}
norm = sqrt(sum);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
