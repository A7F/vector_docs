# DoIP_GetAliveCheckTimeout, DoIP_SetAliveCheckTimeout

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_GetAliveCheckTimeout, DoIP_SetAliveCheckTimeout

**Valid for**: CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetAliveCheckTimeout(dword toAliveCheck_ms);
dword DoIP_GetAliveCheckTimeout();
```

## Description

Sets or returns Alive Check Timeout (T_TCP_Alive_Check)) in milliseconds.

This function must be called in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Parameters

- **toAliveCheck_ms**: The timeout parameter in milliseconds.

## Return Values

- **Form 1**: —
- **Form 2**: The timeout parameter in milliseconds

## Example

This value can also be configured in the DoIP.INI file.

```plaintext
// Set T_TCP_Alive_Check to 3s
DoIP_SetAliveCheckTimeout( 3000);
```
