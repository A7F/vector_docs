[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCertificateUpdateResIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateCertificateUpdateRes_ISO**

# SCC_CreateCertificateUpdateRes_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```
long SCC_CreateCertificateUpdateRes_ISO 
( byte SessionID[], dword ConfigSection, 
char ResponseCode[], byte EncryptedPrivateKey[], 
byte DHParams[], char ContractID[] )
```

## Description

Creates a Certificate Update Response message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ConfigSection**: Number of the section from the test configuration file to use.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **EncryptedPrivateKey**: The private key that belongs to the new certificate for signature purposes.
- **DHParams**: Diffie Hellman parameter string.
- **ContractID**: ID string of the contract (eMAID).

### Optional Parameters

- **RetryCounter** (long): In case of failure, this denotes when the EVCC should try to get the new Certificate again (number of days).

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
