[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetAnalysIsOnlyVariable.md)

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysSetAnalysisOnlyVariable

# sysSetAnalysisOnlyVariable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void sysSetAnalysisOnlyVariable(SysVarName, long anlyzLocal);
```

## Description

Determines whether the variable is meant to be used for analysis purposes.

If this is true (anlyzLocal is set to 1), and the variable is changed in a CAPL program in the Measurement setup, the value change is not transmitted to the realtime part of CANoe, but used immediately in the analysis area. This is the default.

If it is false (anlyzLocal is set to 0), value changes are always transmitted to the realtime part.

**Note**: [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md).

## Parameters

- **anlyzLocal**: Defines whether the variable shall be used only in the analysis area of CANoe.
- **SysVarName**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::".

## Return Values

—

## Example

```plaintext
sysSetAnalysisOnlyVariable(sysvar::MyNamespace::StringVar, 1);
```
