# DoIP_GetReconnectDelay, DoIP_SetReconnectDelay

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetReconnectDelay(dword reconnectDelay_ms);
dword DoIP_GetReconnectDelay();
```

## Description

Sets or returns the delay started by the tester when the ECU closes the TCP connection. After the configured time the tester attempts at first to re-open the TCP connection and afterwards to re-establish the routing activation. If re-opening the TCP connection fails, the number of further attempts and their interval can be configured with [DoIP_SetReconnectInterval](CAPLfunctionDoIPGetSetReconnectInterval.md).

## Parameters

- **reconnectDelay_ms**  
  Delay in milliseconds between TCP connection close and attempt to reactivate it. A value of 0 will deactivate this feature, i.e. the tester does not try to reactivate the route.

## Return Values

- **Form 1**  
  —
  
- **Form 2**  
  TCP reconnection delay

## Example

This value can also be configured in the DoIP.INI file.  
See [DoIP_GetReconnectInterval](CAPLfunctionDoIPGetSetReconnectInterval.md).

[DoIP_GetReconnectInterval](CAPLfunctionDoIPGetSetReconnectInterval.md) • [DoIP_SetReconnectInterval](CAPLfunctionDoIPGetSetReconnectInterval.md)
