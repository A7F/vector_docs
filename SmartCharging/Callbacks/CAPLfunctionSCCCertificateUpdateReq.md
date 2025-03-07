[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCertificateUpdateReq.md)

## SCC_CertificateUpdateReq

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_CertificateUpdateReq

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
void SCC_CertificateUpdateReq ( byte SessionID[], char ContractID[] )
```

### Description

The callback is called as soon as a Certificate Installation Request is received.

The list of root certificate IDs can be queried with the following functions:

- [SCC_GetNumberOfRootCertificateIDs](../Functions/CAPLfunctionSCCGetNumberOfRootCertificateIDs.md)
- [SCC_GetRootCertificateID](../Functions/CAPLfunctionSCCGetRootCertificateID.md)

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ContractID**: ID of the contract to which the certificate is assigned, max. 128 character string. (eMAID)

### Return Values

—

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)