[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreatePaymentDetailsResIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreatePaymentDetailsRes_ISO**

# SCC_CreatePaymentDetailsRes_ISO

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long SCC_CreatePaymentDetailsRes_ISO 
( byte SessionID[], char ResponseCode[], 
byte GenChallenge[], long Timestamp )
```

## Description

Creates a Payment Details Request message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **GenChallenge**: Challenge data (max. 16 byte).
- **Timestamp**: Timestamp of the current charge point time.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
