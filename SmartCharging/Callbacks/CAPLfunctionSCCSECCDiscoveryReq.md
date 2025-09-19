[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSECCDiscoveryReq.md)

## SCC_SECCDiscoveryReq

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_SECCDiscoveryReq

**Valid for**:  CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_SECCDiscoveryReq ( dword TLSEnabled, dword TransportProtocol )
```

### Description

The callback is called as soon as a **SECC Discovery** Request is received.

### Parameters

- **TLSEnabled**: 1 for TLS, 0 for **no transport layer security**.
- **TransportProtocol**: 0 for TCP, 0x10 for UDP.

### Return Values

—

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
