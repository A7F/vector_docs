[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCertificateUpdateRes.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_CertificateUpdateRes

# SCC_CertificateUpdateRes

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CertificateUpdateRes ( byte SessionID[], long ResponseCode, char ContractID[])
```

## Description

The callback is called as soon as a Certificate Installation Response is received.

Further details that are transmitted in this response can be queried with the following functions:

- [SCC_GetDHPublicKey](../Functions/CAPLfunctionSCCGetDHPublicKey.md)
- [SCC_GetEncryptedPrivateKey](../Functions/CAPLfunctionSCCGetEncryptedPrivateKey.md)
- [SCC_GetEMAIDIdAttr](../Functions/CAPLfunctionSCCGetEMAIDIdAttr.md)
- [SCC_GetResponseCodeString](../Functions/CAPLfunctionSCCGetResponseCodeString.md)

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: 1 if **OK**, 0 if **FAILED**
- **ContractID**: ID of the contract to which the certificate is assigned, max. 128 character string. (eMAID)

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
