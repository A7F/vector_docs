[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreatePaymentServiceSelectionResISO.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » SCC_CreatePaymentServiceSelectionRes_ISO

# SCC_CreatePaymentServiceSelectionRes_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreatePaymentServiceSelectionRes_ISO 
( byte SessionID[], char ResponseCode[] )
```

## Description

Creates a Payment Service Selection Response message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
