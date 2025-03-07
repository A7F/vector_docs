[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableString.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableString

# sysGetVariableString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysGetVariableString(char namespace[], char variable[], char buffer[], long bufferSize); // form 1`
- `long sysGetVariableString(SysVarName, char buffer[], long bufferSize); // form 2`

## Description

Returns the value of a variable of the String (char[]) type.

**Note**

- [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md). An access to the whole string is with this variant not possible.
- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember::** instead of **sysvar::**.
  
  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **buffer**: Buffer that takes the value of the variable.
- **bufferSize**: Size of the buffer.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: no error, function successful
- **1**: namespace was not found or second try to define the same namespace
- **2**: variable was not found or second try to define the same variable
- **3**: no writing right for the namespace available
- **4**: the variable has no suitable type for the function

## Example

**Example 1**

`sysGetVariableString(sysvar::MyNamespace::StringVar, buf, elcount(buf));`

**Example 2**

This example shows the use of system variable types as a return value of functions and as a local variable.

The user-defined CAPL function **getSysVarString** returns any system variable of type **String**. The function is therefore defined with the system variable type **sysvarString** as the return value.

The system variable **sv1** (defined with system variable type **String**) represents any system variable depending on the counter of the **getSysVarString** function.

The value of a system variable is set with the CAPL function **sysSetVariableString**.

The value of the system variable is get with the CAPL function **sysGetVariableString** and output in the Write Window.

**Note**

You must define the system variables **FMW1::KeyString**, **DCM::SpeedSignalString**, and **Engine::EngineString** in the [System Variables Configuration](../../../Shared/SystemVariables/SysVarConfigUserDefined.md) dialog first.

```plaintext
on key 'd'
{
  sysvarString * svString1;
  char valueSysVarString[100];
  char buf[100];
  svString1 = getSysVarString(0);
  sysGetVariableString(svString1, buf, elcount(buf));
  write("Variable is %s, Value is %s", svString1.name, buf);
  sysSetVariableString(svString1, "OFF");
  sysGetVariableString(svString1, buf, elcount(buf));
  write("Variable is %s, Value is now: %s", svString1.name, buf);
  svString1 = getSysVarString(1);
  sysGetVariableString(svString1, buf, elcount(buf));
  write("Variable is %s, Value is %s", svString1.name, buf);
  svString1 = getSysVarString(2);
  sysGetVariableString(svString1, buf, elcount(buf));
  write("Variable is %s, Value is %s", svString1.name, buf);
}

sysvarString * getSysVarString(int cKey)
{
  switch (cKey)
  {
    case 0:
      return sysvar::FMW1::KeyString;
    case 1:
      return sysvar::DCM::SpeedSignalString;
    default:
      return sysvar::Engine::EngineStateString;
  }
}
```

[sysSetVariableString](CAPLfunctionSysSetVariableString.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)