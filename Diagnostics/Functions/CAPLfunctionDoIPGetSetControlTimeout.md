[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPGetSetControlTimeout.md)

## DoIP_GetControlTimeout, DoIP_SetControlTimeout

**CAPL Functions** » **Diagnostics** » DoIP_GetControlTimeout, DoIP_SetControlTimeout

**Valid for**: CANoe DE

### Note

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

### Function Syntax

```plaintext
void DoIP_SetControlTimeout(dword toControl_ms);
dword DoIP_GetControlTimeout();
```

### Description

Sets or returns the timeout for Vehicle Identification Requests, connect and routing activation (in milliseconds).

### Parameters

- **toControl_ms**: Timeout for Vehicle Identification Requests, connect and routing activation [ms]

### Return Values

- **Form 1**: —
- **Form 2**: Timeout for Vehicle Identification Requests, connect and routing activation [ms].

### Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
