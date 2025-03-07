[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPGetSetDiagnosticMessageTimeout.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_GetDiagnosticMessageTimeout, DoIP_SetDiagnosticMessageTimeout

# DoIP_GetDiagnosticMessageTimeout, DoIP_SetDiagnosticMessageTimeout

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetDiagnosticMessageTimeout(dword toDiagnosticMessage);
dword DoIP_GetDiagnosticMessageTimeout();
```

## Description

Sets or returns the diagnostic/session layer timeout in a tester waiting for the confirmation that the ECU received a diagnostic request. The timer starts after the diagnostic request was handed over to the DoIP/TP layer of the tester and the confirmation is given after a diagnostic message positive or negative acknowledgment was entirely received by the diagnostic/session layer of the tester.

**Note**: As the timer already starts when physical transmission of the request has not been completed (maybe not even been started) by the DoIP/TP layer, it is necessary to consider the amount of data sent by the tester in order to avoid unexpected timeouts in case of long diagnostic requests.

## Parameters

- **toDiagnosticMessage**: An ACK is expected within this amount of milliseconds [ms].

## Return Values

- **Form 1**: —
- **Form 2**: Timeout waiting for a diagnostic message positive or negative acknowledgment.

## Example

This value can also be configured in the DoIP.INI file.

```plaintext
// Expect an ACK within 1 second
DoIP_SetDiagnosticMessageTimeout(1000);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)