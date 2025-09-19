[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCWeldingDetectionReq.md)

## SCC_WeldingDetectionReq

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_WeldingDetectionReq

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_WeldingDetectionReq ( byte SessionID[] )
```

### Description

The callback is called as soon as a Welding Detection Request is received.

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF

### Return Values

—

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
