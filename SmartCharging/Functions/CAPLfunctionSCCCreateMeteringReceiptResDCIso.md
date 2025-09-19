[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateMeteringReceiptResDCIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateMeteringReceiptResDC_ISO**

# SCC_CreateMeteringReceiptResDC_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```
long SCC_CreateMeteringReceiptResDC_Iso 
( byte SessionID[], char ResponseCode[], 
long NotificationMaxDelay, char StatusCode[], 
char Notification[] )
```

## Description

Creates a Metering Receipt Response message for sending, using the DC syntax.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **NotificationMaxDelay**: Time until the vehicle is expected to react on the notification (for DC_EVSEStatus).
- **StatusCode**: Internal state of the EVSE (for DC_EVSEStatus).
- **Notification**: Notification about an action that the charge point wants the vehicle to perform (for DC_EVSEStatus).

### Optional Parameters

- **Index**: 0
- **Name**: IsolationStatus
- **Type**: char[]
- **Description**: Current isolation condition.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
