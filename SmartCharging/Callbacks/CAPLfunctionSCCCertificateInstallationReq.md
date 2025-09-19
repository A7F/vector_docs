[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCertificateInstallationReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » **SCC_CertificateInstallationReq**

# SCC_CertificateInstallationReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```c
void SCC_CertificateInstallationReq(byte SessionID[])
```

## Description

The callback is called as soon as a Certificate Installation Request is received.

The list of root certificate IDs can be queried with the following functions:

- [SCC_GetOEMPRovisioningCertificate](../Functions/CAPLfunctionSCCGetOEMPRovisioningCertificate.md)
- [SCC_GetNumberOfRootCertificateIDs](../Functions/CAPLfunctionSCCGetNumberOfRootCertificateIDs.md)
- [SCC_GetRootCertificateID](../Functions/CAPLfunctionSCCGetRootCertificateID.md)

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
