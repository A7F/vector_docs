[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPTlsHandshakeCompleted.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _DoIP_TlsHandshakeCompleted

# _DoIP_TlsHandshakeCompleted

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void _DoIP_TlsHandshakeCompleted (dword handshakeResult);
```

## Description

The callback function is called when a **TLS** handshake is completed for the DoIP connection.

## Parameters

- **handshakeResult**  
  TLS handshake result. If the operation completed successfully the value is zero. Otherwise, the value is an error code.

## Return Values

—

## Example

```plaintext
void _DoIP_TlsHandshakeCompleted(dword handshakeResult)
{
  write( "[%.3f] TLS handshake completed with result '%i'", timenow()/100000.0, handshakeResult);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)