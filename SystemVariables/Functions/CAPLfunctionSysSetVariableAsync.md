[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetVariableAsync.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysSetVariableAsync

# sysSetVariableAsync

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void sysSetVariableAsync(SysVarName, byte data[], long size); // form 1`
- `void sysSetVariableAsync(SysVarName, float value); // form 2`
- `void sysSetVariableAsync(SysVarName, float values[], long arraySize); // form 3`
- `void sysSetVariableAsync(SysVarName, long value); // form 4`
- `void sysSetVariableAsync(SysVarName, long values[], long arraySize); // form 5`
- `void sysSetVariableAsync(SysVarName, int64 value); // form 6`
- `void sysSetVariableAsync(SysVarName, char value[]); // form 7`

## Description

Assigns the given value (data, value or values[]) to the system variable with identifier **SysVarName**. The bytes of data buffers are copied to struct, generic data and byte array system variables (form 1). The content of a character string is copied to String system variables (form 7). Floating point or integer numbers and arrays are assigned to the corresponding types of system variables (form 2 – 6).

The assignment is executed asynchronously. When [measurement setup parallelization](../../../CANoeCANalyzer/Windows/MeasurementSetup/LoggingBranchParallelization.md) is activated, other branches in the measurement setup will see the new value earlier or later than the branch where the function is called.

In contrast to `sysSetVariable*` functions, `sysSetVariableAsync` do not prevent a measurement setup branch from being parallelized.

**Note**

`sysSetVariableAsync` is useful to set system variables during the simulation and read their value using the [System](../../../COMInterface/Objects/COMObjectSystem.md) COM object after the simulation has been stopped. For this purpose, system variables have to be configured to be used for analysis only.

The `sysSetVariableAsync` function can also be used for specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. If you directly give the element name to the function instead of using strings, precede the name by `sysvarMember::` instead of `sysvar::`.

**Example**

`sysvarMember::XCP::ECU_2::KL2.Curve2[0]`

## Parameters

- **SysVarName**: System variable name. Must exist in the database.
- **data, value or values[]**: New value for the system variable (form 1, 2) or buffer with new data (form 3, 4).
- **size**: The number of bytes to be copied (form 1).
- **arraySize**: The number of elements to be copied (form 3, 5).

## Return Values

—

## Example

```c
byte dataBuf[64];
...

// Assign the value 0 to system variable Switch
sysSetVariableAsync(sysvar::Switch, 0);

// Assign the value 22.5 to system variable Temperature
sysSetVariableAsync (sysvar::Temperature, 22.5);

// Assign the value Master to system variable NodeName
sysSetVariableAsync (sysvar::NodeName, "Master");

// Copy 64 bytes of the data buffer into the system variable DiagData
sysSetVariableAsync (sysvar::DiagData, dataBuf, 64);

...
```

[Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
