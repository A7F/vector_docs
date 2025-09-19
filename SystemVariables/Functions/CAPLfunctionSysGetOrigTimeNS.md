[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetOrigTimeNS.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetOrigTimeNS

# sysGetOrigTimeNS

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
int64 sysGetOrigTimeNS(SysVarName);
```

## Description

Returns the original time stamp of the last update to the variable value, before time synchronization may have changed it.

## Parameters

- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

Original time stamp of the last update to the variable value in nanoseconds since measurement start.

## Example

```c
int64 timeStamp;
timeStamp = sysGetOrigTimeNS(sysvar::MyNamespace::FloatVar);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
