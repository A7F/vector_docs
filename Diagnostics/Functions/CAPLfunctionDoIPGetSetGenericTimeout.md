# DoIP_GetGenericTimeout, DoIP_SetGenericTimeout

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetGenericTimeout( dword toGeneric_ms); // form 1
dword DoIP_GetGenericTimeout();  // form 2
```

## Description

Sets or returns the generic timeout. The generic timeout specifies the maximum time of inactivity of the TCP connection before the connection is automatically closed.

## Parameters

- **toGeneric_ms**: The timeout parameter in milliseconds.

## Return Values

- **Form 1**: —
- **Form 2**: Timeout waiting for a diagnostic message positive or negative acknowledgment.

## Example

This value can also be configured in the DoIP.INI file.

```plaintext
// Set T_TCP_Generic_Inactivity to 30s
DoIP_SetGenericTimeout( 30000);
```
