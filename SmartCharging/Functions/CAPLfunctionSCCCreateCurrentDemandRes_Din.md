[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCurrentDemandRes_Din.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » SCC_CreateCurrentDemandRes_DIN

# SCC_CreateCurrentDemandRes_DIN

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateCurrentDemandRes_DIN 
( byte SessionID[], char ResponseCode[], 
long NotificationMaxDelay, char StatusCode[], 
char Notification[], float PresentVoltage, 
float PresentCurrent, 
byte LimitAchievedFlags[] )
```

## Description

Creates a Current Demand Request message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **NotificationMaxDelay**: Time until the vehicle is expected to react on the notification (for DC_EVSEStatus).
- **StatusCode**: Internal state of the EVSE (for DC_EVSEStatus).
- **Notification**: Notification about an action that the charge point wants the vehicle to perform (for DC_EVSEStatus).
- **PresentVoltage**: EVSEPresentVoltage
- **PresentCurrent**: EVSEPresentCurrent
- **LimitAchievedFlags**: Flags that indicate if any limit is achieved:
  - LimitAchievedFlags [0] = EVSECurrentLimitAchieved
  - LimitAchievedFlags [1] = EVSEVoltageLimitAchieved
  - LimitAchievedFlags [2] = EVSEPowerLimitAchieved

### Optional Parameters

| Index | Name             | Type   | Description                  |
|-------|------------------|--------|------------------------------|
| 0     | IsolationStatus  | char[] | Current isolation condition. |
| 1     | MaxVoltage       | float  | EVSEMaximumVoltageLimit      |
| 2     | MaxCurrent       | float  | EVSEMaximumCurrentLimit      |
| 3     | MaxPower         | float  | EVSEMaximumPowerLimit        |

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
