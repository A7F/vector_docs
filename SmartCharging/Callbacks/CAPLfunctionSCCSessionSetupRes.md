[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSessionSetupRes.md)

## SCC_SessionSetupRes

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_SessionSetupRes

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

### Function Syntax

```plaintext
void SCC_SessionSetupRes ( byte SessionID[], long ResponseCode, char EVSEID[] )
```

### Description

The callback is called as soon as a Session Setup Response is received. Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetTimestamp](../Functions/CAPLfunctionSCCGetTimestamp.md).
- [SCC_GetResponseCodeString](../Functions/CAPLfunctionSCCGetResponseCodeString.md).

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: 1 if **OK**, 0 if **FAILED**.
- **EVSEID**: ID of charge point.

### Return Values

—

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
