[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetVariableData.md)

**CAPL Functions** » **System Variables** » **sysSetVariableData**

# sysSetVariableData

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysSetVariableData(char namespace[], char variable[], byte data[], long size); // form 1`
- `long sysSetVariableData(SysVarName, byte data[], long size); // form 2`

## Description

Sets the value of a variable of the type data, string, struct or generic array.

**Note**

- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember::** instead of **sysvar::**.

  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`

- For variables of type **string**, the raw bytes of the string are set. The string value must either be encoded in UTF-8 or in the current active codepage of the computer, depending on the setting in the **Options** dialog (String Encoding). A terminating 0 is optional.
- For variables of type **struct** that contain a member of type **data**, a maximum length must be specified when defining this structure member.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **data**: New values for the variable.
- **size**: New size for the variable. Must not exceed the length of the data array.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: no error, function successful
- **1**: namespace was not found or second try to define the same namespace
- **2**: variable was not found or second try to define the same variable
- **3**: no writing right for the namespace available
- **4**: the variable has no suitable type for the function

## Example

This example shows the use of system variable types as a return value of functions and as a local variable.

The user-defined CAPL function **getSysVarData** returns any system variable of type **Data**. The function is therefore defined with the system variable type **sysvarData** as the return value.

The system variable **sv1** (defined with system variable type **Data**) represents any system variable depending on the counter of the **getSysVarData** function.

The value of a system variable is set with the CAPL function **sysSetVariableData**.

The value of the system variable is get with the CAPL function **sysGetVariableData** and output in the Write Window.

**Note**

You must define the system variables **FMW1::KeyData**, **DCM::SpeedSignalData**, and **Engine::EngineData** in the [System Variables Configuration](../../../Shared/SystemVariables/SysVarConfigUserDefined.md) dialog first.

```plaintext
on key 'e'
{
  sysvarData * svData1;
  char valueSysVarData[100];
  byte buf[2];
  long size = 2;
  long copiedBytes;
  byte data[2] = {0xAF, 0xEF};
  svData1 = getSysVarData(0);
  sysGetVariableData(svData1, buf, copiedBytes);
  write("Variable is %s, Value is %x", svData1.name, buf[0]);
  sysSetVariableData(svData1, data, size);
  sysGetVariableData(svData1, buf, copiedBytes);
  write("Variable is %s, Value is now: %x", svData1.name, buf[0]);
  svData1 = getSysVarData(1);
  sysGetVariableData(svData1, buf, copiedBytes);
  write("Variable is %s, Value is %x", svData1.name, buf[0]);
  svData1 = getSysVarData(2);
  sysGetVariableData(svData1, buf, copiedBytes);
  write("Variable is %s, Value is %x", svData1.name, buf[0]);
}

sysvarData * getSysVarData(int eKey)
{
  switch (eKey)
  {
    case 0:
      return sysvar::FMW1::KeyData;
    case 1:
      return sysvar::DCM::SpeedSignalData;
    default:
      return sysvar::Engine::EngineStateData;
  }
}
```

[sysGetVariableData](CAPLfunctionSysGetVariableData.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
