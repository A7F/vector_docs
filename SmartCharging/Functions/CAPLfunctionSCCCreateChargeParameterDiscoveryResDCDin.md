[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateChargeParameterDiscoveryResDCDin.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » SCC_CreateChargeParameterDiscoveryResDC_DIN

# SCC_CreateChargeParameterDiscoveryResDC_DIN

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```
long SCC_CreateChargeParameterDiscoveryResDC_DIN ( byte SessionID[], char ResponseCode[], long NotificationMaxDelay, char StatusCode[], char Notification[], long EVSEProcessing, float CurrentAndVoltageLimits[], float PeakCurrentRipple)
```

## Description

Creates a Charge Parameter Discovery Response message for sending, using the DC syntax.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **NotificationMaxDelay**: Time until the vehicle is expected to react on the notification (for DC_EVSEStatus).
- **StatusCode**: Internal state of the EVSE (for DC_EVSEStatus).
- **Notification**: Notification about an action that the charge point wants the vehicle to perform (for DC_EVSEStatus).
- **EVSEProcessing**:
  - 0 if **Finished**
  - 1 if **Ongoing**
  - 2 if **Ongoing_WaitingForCustomerInteraction** (ISO 15118)
- **CurrentAndVoltageLimits**: Electrical limit values
  - CurrentAndVoltageLimits[0] = EVSEMaximumCurrentLimit
  - CurrentAndVoltageLimits[1] = EVSEMaximumVoltageLimit
  - CurrentAndVoltageLimits[2] = EVSEMinimumCurrentLimit
  - CurrentAndVoltageLimits[3] = EVSEMinimumVoltageLimit
  - **Only for ISO 15118**: CurrentAndVoltageLimits[4] = EVSEMaximumPowerLimit
- **PeakCurrentRipple**: Peak-to-peak magnitude of the current ripple.

### Optional Parameters

| Index | Name                       | Type   | Description                                           |
|-------|----------------------------|--------|-------------------------------------------------------|
| 0     | MaxPower                   | float  | EVSEMaximumPowerLimit                                 |
| 1     | CurrentRegulation- Tolerance | float  | Absolute magnitude of the regulation tolerance.       |
| 2     | EnergyToBeDelivered        | float  | Amount of energy to be delivered in Wh.               |
| 3     | SAScheduleList             | long   | Schedule / tariff list from secondary actor.          |
| 4     | EVSEIsolationStatus        | char[] | Indicates the isolation condition.                    |

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—
