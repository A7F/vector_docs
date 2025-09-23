[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetVariableLong.md)

## sysSetVariableLong

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysSetVariableLong

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

- `long sysSetVariableLong(char namespace[], char variable[], long value); // form 1`
- `long sysSetVariableLong(SysVarName, long value); // form 2`

### Description

Sets the value of a system variable of type long (32bit signed integer).

**Note**

- [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md).
- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by `sysvarMember::` instead of `sysvar::`.
  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`
- The function can also be used for variables of type unsigned integer. You can simply cast the value to long.

### Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **value**: New value of the variable.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

### Return Values

- **0**: no error, function successful
- **1**: namespace was not found or second try to define the same namespace
- **2**: variable was not found or second try to define the same variable
- **3**: no writing right for the namespace available
- **4**: the variable has no suitable type for the function

### Example

**Example 1**

```plaintext
long lVar;
...
sysSetVariableLong(sysvar::MyNamespace::IntVar, lVar);
```

**Example 2**

This example shows the use of system variable types as a return value of functions and as a local variable.

The user-defined CAPL function **getSysVar** returns any system variable of type **Int**. The function is therefore defined with the system variable type **sysvarInt** as the return value.

The system variable **sv1** (defined with system variable type **Int**) represents any system variable depending on the counter of the **getSysVar** function.

The value of a system variable is set with the CAPL function **sysSetVariableLong**.

The value of the system variable is get with the CAPL function **sysGetVariableLong** and output in the Write Window.

**Note**

You must define the system variables **FMW1::Key**, **DCM::SpeedSignal**, and **Engine::EngineStateSwitch** in the [System Variables Configuration](../../../Shared/SystemVariables/SysVarConfigUserDefined.md) dialog first.

```plaintext
on key 'a'
{
  sysvarInt * sv1; //defines a local system variable 'sv1' with the system variable type 'sysvarInt'
  int  valueSysVar;
  sv1 = getSysVar(0);
  write("Variable is %s, Value is %d", sv1.name, @sv1);
  //@sv1++;
  sysSetVariableLong(sv1, @sv1+1);
  write("Variable is %s, Value is higher: %d", sv1.name, @sv1);
  sv1 = getSysVar(1);
  write("Variable is %s, Value is %d", sv1.name, @sv1);
  sv1 = getSysVar(2);
  valueSysVar = sysGetVariableLong(sv1);
  write("Variable is %s, Value is %d", sv1.name, valueSysVar);
}

sysvarInt * getSysVar(int aKey)
{
  switch (aKey)
  {
  case 0:
    return sysvar::FMW1::Key;
  case 1:
    return sysvar::DCM::SpeedSignal;
  default:
    return sysvar::Engine::EngineStateSwitch;
  }
}
```

[sysGetVariableLong](CAPLfunctionSysGetVariableLong.md)
