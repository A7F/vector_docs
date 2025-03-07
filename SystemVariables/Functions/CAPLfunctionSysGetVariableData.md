[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableData.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableData

# sysGetVariableData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysGetVariableData(char namespace[], char variable[], byte buffer[], long& copiedBytes); // form 1`
- `long sysGetVariableData(SysVarName, byte buffer[], long& copiedBytes); // form 2`

## Description

Returns the value of a variable of the type data, string, struct or generic array.

**Note**

- The function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by **sysvarMember::** instead of **sysvar::**.  
  **Example**: `sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0]`
- For variables of type string, the raw bytes of the string are returned. The value is either encoded in UTF-8 or in the current active codepage of the computer, depending on the setting in the [Options](../../../CANoeCANalyzer/Ribbon/File/Options/Measurement/MeasurementGeneralSettings.md) dialog (String Encoding). The bytes include a terminating 0.

## Parameters

- **namespace**: Name of the namespace.
- **variable**: Name of the variable.
- **buffer**: Buffer which takes the value of the variable.
- **copiedBytes**: Receives the number of bytes which were copied into the buffer. If the buffer is too small, no bytes will be copied; else the parameter will contain the current size of the variable.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

- **0**: no error, function successful
- **1**: namespace was not found or second try to define the same namespace
- **2**: variable was not found or second try to define the same variable
- **3**: no writing right for the namespace available
- **4**: the variable has no suitable type for the function
- **5**: the buffer is too small for the value

## Example

—

[sysSetVariableData](CAPLfunctionSysSetVariableData.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)