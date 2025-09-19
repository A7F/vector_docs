[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateAuthorizationResISO.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » SCC_CreateAuthorizationRes_ISO

# SCC_CreateAuthorizationRes_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateAuthorizationRes_ISO 
( byte SessionID[], char ResponseCode[], 
long EVSEProcessing )
```

## Description

Creates an Authorization Response message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **EVSEProcessing**:
  - 0 if **Finished**
  - 1 if **Ongoing**
  - 2 if **Ongoing_WaitingForCustomerInteraction** (ISO 15118).

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
