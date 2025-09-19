[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCertificateUpdateReqIso.md)

## SCC_CreateCertificateUpdateReq_ISO

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » SCC_CreateCertificateUpdateReq_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
long SCC_CreateCertificateUpdateReq_ISO ( byte SessionID[], dword ConfigSection, char ContractID[], char MessageID[] )
```

### Description

Creates a Certificate Update Request message for sending.

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ConfigSection**: Number of the section from the test configuration file to use.
- **ContractID**: ID string of the contract (eMAID).
- **MessageID**: ID attribute for this message.

### Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
