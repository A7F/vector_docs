[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSECCDiscoveryRes.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_SECCDiscoveryRes

# SCC_SECCDiscoveryRes

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```c
void SCC_SECCDiscoveryRes ( dword TLSEnabled, dword TransportProtocolType )
```

## Description

The callback is called as soon as an SECC Discovery Response is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetEVSEIP](../Functions/CAPLfunctionSCCGetEVSEIP.md)
- [SCC_GetEVSEPort](../Functions/CAPLfunctionSCCGetEVSEPort.md)

## Parameters

- **TLSEnabled**: 1 for TLS, 0 for **no transport layer security**.
- **TransportProtocol**: 0 for TCP, 0x10 for UDP.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
