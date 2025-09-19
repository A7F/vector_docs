[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetCertificateChainCertificate.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » SCC_GetCertificateChainCertificate

# SCC_GetCertificateChainCertificate

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_GetCertificateChainCertificate ( long Target, long Index, char Certificate[] )
```

## Description

## Parameters

- **Index**: Index of the target certificate, where 0 denotes the parent certificate, and 1..4 denote sub-certificates.
- **Target**: Set this according to the type of certificate chain that is queried:
  - 0 = ContractSignatureCertChain
  - 1 = SAProvisioningCertChain (EV and ISO 15118 only)
- **Certificate**: Queries the target certificate as base64 string (to the given char buffer).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
