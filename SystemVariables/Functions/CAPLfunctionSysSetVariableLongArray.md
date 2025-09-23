[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetVariableLongArray.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysSetVariableLongArray

# sysSetVariableLongArray

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysSetVariableLongArray(char namespace[], char variable[], long values[], long arraySize); // form 1`
- `long sysSetVariableLongArray(SysVarName, long values[], long arraySize); // form 2`

## Description

Sets the value of a variable of the `long[]` type.

The call will only succeed if the array size given as parameter is equal to the actual array size of the system variable (you cannot change that size dynamically). The current values of the system variable will then be set to the elements in the **values** array in the range from 0 to **arraySize**.

Never give as parameter an array size which is larger than real size of the **values** array, this would lead to unpredictable behavior.

**Note**

- [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md). An access to the whole array is with this variant not possible.
- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember::** instead of **sysvar::**.
  
  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **values**: Values of the variable.
- **arraySize**: Number of values in the array.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: no error, function successful
- **1**: namespace was not found or second try to define the same namespace
- **2**: variable was not found or second try to define the same variable
- **3**: no writing right for the namespace available
- **4**: the variable has no suitable type for the function

## Example

**Example 1**

```plaintext
long lVarArr[10];
...
sysSetVariableLongArray(sysvar::MyNamespace::LongArrayVar, lVarArr, elcount(lVarArr));
```

**Example 2**

This example shows the use of system variable types as a return value of functions and as a local variable.

The user-defined CAPL function **getSysVarIntArray** returns any system variable of type **IntArray**. The function is therefore defined with the system variable type **sysvarIntArray** as the return value.

The system variable **sv1** (defined with system variable type **IntArray**) represents any system variable depending on the counter of the **getSysVarIntArray** function.

The value of a system variable is set with the CAPL function **sysSetVariableLongArray**.

The value of the system variable is get with the CAPL function **sysGetVariableLongArray** and output in the Write Window.

**Note**

You must define the system variables **FMW1::KeyIntegerArray**, **DCM::SpeedSignalIntegerArray**, and **Engine::EngineIntegerArray** in the [System Variables Configuration](../../../Shared/SystemVariables/SysVarConfigUserDefined.md) dialog first.

```plaintext
on key 'f'
{
  sysvarIntArray * sv1;
  long lVarArr [5] = {7, 7, 7, 7, 7};
  sv1 = getSysVarIntArray(0);
  write("Variable is %s%s, Value is %d", sv1.name, "[0]", @sv1[0]);
  sysSetVariableLongArray(sv1,lVarArr, elcount(lVarArr));
  write("Variable is %s%s, Value is: %d", sv1.name, "[0]",@sv1[0]);
  sv1 = getSysVarIntArray(1);
  write("Variable is %s%s, Value is %d", sv1.name, "[0]", @sv1[0]);
  sv1 = getSysVarIntArray(2);
  sysGetVariableLongArray (sv1, lVarArr, elcount(lVarArr));
  write("Variable is %s%s, Value is %d", sv1.name, "[0]",lVarArr[0]);
}

sysvarIntArray * getSysVarIntArray (int fKey)
{
  switch (fKey)
  {
  case 0:
    return sysvar::FMW1::KeyIntegerArray;
  case 1:
    return sysvar::DCM::SpeedSignalIntegerArray;
  default:
    return sysvar::Engine::EngineIntegerArray;
  }
}
```

[sysGetVariableLongArray](CAPLfunctionSysGetVariableLongArray.md)
