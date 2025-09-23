[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableFloatArray.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableFloatArray

# sysGetVariableFloatArray

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysGetVariableFloatArray(char namespace[], char variable[], float values[], long arraySize); // form 1`
- `long sysGetVariableFloatArray(SysVarName, float values[], long arraySize); // form 2`

## Description

Returns the value of a variable of the float[] type.

If the actual array size of the system variable is larger than the array size given as parameter, all elements in the **values** array up to the array size given as parameter will receive the current values of the system variable. Elements in the **values** array beyond the array size given as parameter will remain unchanged.

If the actual array size of the system variable is smaller than the array size given as parameter, additional elements in the **values** array will be set to 0. Elements in the **values** array beyond the array size given as parameter will remain unchanged.

Never give as parameter an array size which is larger than real size of the **values** array, this would lead to unpredictable behavior.

**Note**

- [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md). An access to the whole array is with this variant not possible.
- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember::** instead of **sysvar::**.

  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **values**: Gets the values of the variable.
- **arraySize**: Size of the array.
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
float fVarArr[10]; // array size should match the size of the system variable
...
sysGetVariableFloatArray(sysvar::MyNamespace::FloatArrayVar, fVarArr, elcount(fVarArr));
```

**Example 2**

This example shows the use of system variable types as a return value of functions and as a local variable.

The user-defined CAPL function **getSysVarFloatArray** returns any system variable of type **FloatArray**. The function is therefore defined with the system variable type **sysvarFloatArray** as the return value.

The system variable **sv1** (defined with system variable type **FloatArray**) represents any system variable depending on the counter of the **getSysVarFloatArray** function.

The value of a system variable is set with the CAPL function **sysSetVariableFloatArray**.

The value of the system variable is get with the CAPL function **sysGetVariableFloatArray** and output in the Write Window.

**Note**

You must define the system variables **FMW1::KeyFloatArray**, **DCM::SpeedSignalFloatArray**, and **Engine::EngineFloatArray** in the [System Variables Configuration](../../../Shared/SystemVariables/SysVarConfigUserDefined.md) dialog first.

```plaintext
on key 'g'
{
  sysvarFloatArray * sv1;
  float fVarArr [5] = {7.3, 7.3, 7.3, 7.3, 7.3};
  sv1 = getSysVarFloatArray(0);
  write("Variable is %s%s, Value is %2.1lf", sv1.name, "[0]", @sv1[0]);
  sysSetVariableFloatArray(sv1,fVarArr, elcount(fVarArr));
  write("Variable is %s%s, Value is: %2.1lf", sv1.name, "[0]",@sv1[0]);
  sv1 = getSysVarFloatArray(1);
  write("Variable is %s%s, Valgue is %2.1lf", sv1.name, "[0]", @sv1[0]);
  sv1 = getSysVarFloatArray(2);
  sysGetVariableFloatArray (sv1, fVarArr, elcount(fVarArr));
  write("Variable is %s%s, Value is %2.1lf", sv1.name, "[0]",fVarArr[0]);
}

sysvarFloatArray * getSysVarFloatArray (int gKey)
{
  switch (gKey)
  {
  case 0:
    return sysvar::FMW1::KeyFloatArray;
  case 1:
    return sysvar::DCM::SpeedSignalFloatArray;
  default:
    return sysvar::Engine::EngineFloatArray;
  }
}
```

[sysSetVariableFloatArray](CAPLfunctionSysSetVariableFloatArray.md)
