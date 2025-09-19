# DoIP_InitAsTester

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_InitAsTester();
```

## Description

Per default the DoIP.DLL will operate as ECU simulation. In order to use this DLL as tester, e.g. in a test module, the operation mode has to be changed by calling this function in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md). It is NOT necessary to call this function when the built-in diagnostics channel is used, i.e. if the DoIP.DLL is not configured in the tester.

## Parameters

—

## Return Values

—

## Example

```plaintext
on preStart
{
  // Make sure the DoIP.DLL does not act as vehicle
  DoIP_InitAsTester();
}
```
