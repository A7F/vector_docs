[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableFloat.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableFloat

# sysGetVariableFloat

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `double sysGetVariableFloat(char namespace[], char variable[]); // form 1`
- `double sysGetVariableFloat(SysVarName); // form 2`
- `long sysGetVariableFloat(char namespace[], char variable[], double& value); // form 3`
- `long sysGetVariableFloat(SysVarName, double& value); // form 4`

## Description

Returns the value of a variable of the double type.

**Note:**

- [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md).
- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember::** instead of **sysvar::**.

  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **namespace**: Name of the namespace (form 1).
- **variable**: Name of the variable (form 1).
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".
- **value**: Receives the current value of the variable.

## Return Values

- **Value of the variable or 0 in case of error (form 1 and 2)**
- **0**: No error, function successful (form 3 and 4)
- **2**: Variable was not found (form 3 and 4)
- **4**: Variable has no suitable type for the function (form 3 and 4)

## Example

**Example 1**

The value of the **FloatVar** system variable will be determined and displayed in the Write Window.

```plaintext
on key 'b'
{
  double value;
  value = SysGetVariableFloat(sysvar::MyNamespace::FloatVar);
  write("Value of FloatVar is %g", value);
}
```

**Example 2**

This example shows the use of system variable types as a return value of functions and as a local variable.

The user-defined CAPL function **getSysVarFloat** returns any system variable of type **Float**. The function is therefore defined with the system variable type **sysvarFloat** as the return value.

The system variable **sv1** (defined with system variable type **Float**) represents any system variable depending on the counter of the **getSysVarFloat** function.

The value of a system variable is set with the CAPL function **sysSetVariableFloat**.

The value of the system variable is get with the CAPL function **sysGetVariableFloat** and output in the Write Window.

**Note:** You must define the system variables **FMW1::KeyFloat**, **DCM::SpeedSignalFloat**, and **Engine::EngineFloat** in the [System Variables Configuration](../../../Shared/SystemVariables/SysVarConfigUserDefined.md) dialog first.

```plaintext
on key 'c'
{
  sysvarFloat * svFloat1;  //defines a local system variable 'sv1Float' with the system variable type 'sysvarFloat'
  float valueSysVar;
  svFloat1 = getSysVarFloat(0);
  //@svFloat1 = 1.5;
  write("Variable is %s, Value is %7.3f", svFloat1.name, @svFloat1);
  //@svFloat1 = @svFloat1*2.5;
  sysSetVariableFloat(svFloat1, @svFloat1*2.5);
  write("Variable is %s, Value is higher: %7.3f", svFloat1.name, @svFloat1);
  svFloat1 = getSysVarFloat(1);
  write("Variable is %s, Value is %7.3f", svFloat1.name, @svFloat1);
  svFloat1 = getSysVarFloat(2);
  valueSysVar = sysGetVariableFloat(svFloat1);
  write("Variable is %s, Value is %d", svFloat1.name, valueSysVar);
}

sysvarFloat * getSysVarFloat(int cKey)
{
  switch (cKey)
  {
    case 0:
      return sysvar::FMW1::KeyFloat;
    case 1:
      return sysvar::DCM::SpeedSignalFloat;
    default:
      return sysvar::Engine::EngineFloat;
  }
}
```

[sysSetVariableFloat](CAPLfunctionSysSetVariableFloat.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
