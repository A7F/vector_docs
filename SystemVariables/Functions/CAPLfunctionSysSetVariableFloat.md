[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetVariableFloat.md)

**CAPL Functions** » **System Variables** » **sysSetVariableFloat**

# sysSetVariableFloat

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long sysSetVariableFloat(char namespace[], char variable[], float value); // form 1
long sysSetVariableFloat(SysVarName, float value); // form 2
```

## Description

Sets the value of a variable of the double type.

**Note**

- [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md).
- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember::** instead of **sysvar::**.

  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **value**: New value of the variable.
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
float fVar;
...
sysSetVariableFloat(sysvar::MyNamespace::FloatVar, fVar);
```

**Example 2**

This example shows the use of system variable types as a return value of functions and as a local variable.

The user-defined CAPL function **getSysVarFloat** returns any system variable of type **Float**. The function is therefore defined with the system variable type **sysvarFloat** as the return value.

The system variable **sv1** (defined with system variable type **Float**) represents any system variable depending on the counter of the **getSysVarFloat** function.

The value of a system variable is set with the CAPL function **sysSetVariableFloat**.

The value of the system variable is get with the CAPL function **sysGetVariableFloat** and output in the Write Window.

**Note**

You must define the system variables **FMW1::KeyFloat**, **DCM::SpeedSignalFloat**, and **Engine::EngineFloat** in the [System Variables Configuration](../../../Shared/SystemVariables/SysVarConfigUserDefined.md) dialog first.

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

[sysGetVariableFloat](CAPLfunctionSysGetVariableFloat.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)