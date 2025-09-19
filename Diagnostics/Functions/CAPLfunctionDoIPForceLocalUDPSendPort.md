# DoIP_ForceLocalUDPSendPort

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long DoIP_ForceLocalUDPSendPort(dword forcedPort);
```

## Description

According to ISO 13400, the local send port for UDP messages should be dynamically selected. This function allows forcing the local UDP send port to a specific value, typically to 13400 to indicate DoIP.

Note that specifying a "well-known" or system port (1..1023) might not work on most systems.

## Parameters

- **forcedPort**
  - `0`: use a dynamically assigned value (default)
  - `1..65535`: bind to this local UDP port
  - other: reserved.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
On preStart
{
  // Make sure that in an ECU simulation all UDP packets are sent from the standard port
  DoIP_ForceLocalUDPSendPort(13400);
}
```

[DoIP_ForceLocalTCPSendPort](CAPLfunctionDoIPForceLocalTCPSendPort.md) • [DoIP_SetLocalIPaddress](CAPLfunctionDoIPSetLocalIPaddress.md)
