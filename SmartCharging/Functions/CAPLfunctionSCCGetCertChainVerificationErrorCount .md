# SCC_GetCertChainVerificationErrorCount

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetCertChainVerificationErrorCount .md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [General Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » SCC_GetCertChainVerificationErrorCount

## Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```
dword SCC_GetCertChainVerificationErrorCount( )
```

### Description
Gets the number of verification errors from the last certificate chain verification, which is indicated by the callback function [SCC_CertChainVerificationInd](../Callbacks/CAPLfunctionSCCCertChainVerificationInd.md).

Individual errors can be queried with [SCC_GetCertChainVerificationError](CAPLfunctionSCCGetCertChainVerificationError.md).

### Parameters
—

### Return Values
—

### Example
—

**Related Links:**

- [SCC_CertChainVerificationInd](../Callbacks/CAPLfunctionSCCCertChainVerificationInd.md)
- [SCC_GetCertChainVerificationError](CAPLfunctionSCCGetCertChainVerificationError.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
