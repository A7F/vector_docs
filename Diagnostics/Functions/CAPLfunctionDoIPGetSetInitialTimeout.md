# DoIP_GetInitialTimeout, DoIP_SetInitialTimeout

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetInitialTimeout( dword toInitial_ms); // form 1
dword DoIP_GetInitialTimeout(); // form 2
```

## Description

Sets or returns the initial timeout, started when a tester connects to the ECU (in milliseconds). A route activation request must be received in this interval, otherwise the TCP connection is closed.

**Note**

If routing activation requests are switched off in the DoIP.INI via **DisableRouteActivation**, this timeout is not checked.

## Parameters

- **toInitial_ms**: The timeout parameter in milliseconds.

## Return Values

- **Form 1**: —
- **Form 2**: Initial timeout

## Example

This value can also be configured in the DoIP.INI file.

```plaintext
// Set T_TCP_Initial_Inactivity to 3s
DoIP_SetInitialTimeout( 3000);
```
