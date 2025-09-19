[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableLong.md)

# sysGetVariableLong

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableLong

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysGetVariableLong(char namespace[], char variable[]); // form 1`
- `long sysGetVariableLong(SysVarName); // form 2`
- `long sysGetVariableLong(char namespace[], char variable[], long& value); // form 3`
- `long sysGetVariableLong(SysVarName, long& value); // form 4`

## Description

Returns the value of a system variable of type long (32bit signed integer).

**Note**

- [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md).
- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by `sysvarMember::` instead of `sysvar::`.

  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

- The function can also be used for variables of type unsigned integer. You can simply cast the result to dword.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".
- **value**: Receives the current value of the variable.

## Return Values

- **Value of the variable or 0 in case of error (form 1 and 2)**

  - **0**: No error, function successful (form 3 and 4)
  - **2**: Variable was not found (form 3 and 4)
  - **4**: Variable has no suitable type for the function (form 3 and 4)

## Example

**Example 1**

```plaintext
sysGetVariableLong("MyNamespace", "IntVar"); // example for form 1
sysGetVariableLong(sysvar::MyNamespace::IntVar); // example for form 2
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

[sysSetVariableLong](CAPLfunctionSysSetVariableLong.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
