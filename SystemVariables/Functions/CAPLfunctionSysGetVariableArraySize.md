[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableArraySize.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableArraySize

# sysGetVariableArraySize

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `dword sysGetVariableArraySize(sysvar variable) // form 1`
- `long sysGetVariableArraySize(char namespace[], char variable[], dword& arraySize) // form 2`

## Description

Retrieves the current array size of a system variable which has a generic array data type.

**Note**

- This function can’t be used for system variables of type Data, IntArray or FloatArray; use [sysGetVariableArrayLength](CAPLfunctionSysGetVariableArrayLength.md) for these.
- The function can also be used for specific elements of a system variable of type struct or generic array. For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember**:: instead of **sysvar**::.
  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **variable (form 1)**  
  Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

- **namespace (form 2)**  
  Name of the namespace

- **variable (form 2)**  
  Name of the variable

- **arraySize (form 2)**  
  Current size of the array (out-parameter)

## Return Values

- **Form 1**  
  Current size of the array

- **Form 2**  
  Error code:
  - 0 – no error
  - 2 – variable not found
  - 4 – variable is not of a generic array type

## Example

—
