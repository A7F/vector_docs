[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateWeldingDetectionResDin.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » SCC_CreateWeldingDetectionRes_DIN

# SCC_CreateWeldingDetectionRes_DIN

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateWeldingDetectionRes_DIN 
( byte SessionID[], char ResponseCode[], 
long NotificationMaxDelay, char StatusCode[], 
char Notification[], float PresentVoltage )
```

## Description

Creates a Welding Detection Response message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **NotificationMaxDelay**: Time until the vehicle is expected to react to the notification (for DC_EVSEStatus).
- **StatusCode**: Internal state of the EVSE (for DC_EVSEStatus).
- **Notification**: Notification about an action that the charge point wants the vehicle to perform (for DC_EVSEStatus).
- **PresentVoltage**: EVSEPresentVoltage

### Optional Parameters

- **Index 0**: 
  - **Name**: IsolationStatus
  - **Type**: char[]
  - **Description**: Current isolation condition.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)