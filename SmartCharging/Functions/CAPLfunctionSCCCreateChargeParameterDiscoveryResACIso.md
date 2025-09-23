[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateChargeParameterDiscoveryResACIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateChargeParameterDiscoveryResAC_ISO**

# SCC_CreateChargeParameterDiscoveryResAC_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateChargeParameterDiscoveryResAC_ISO 
( byte SessionID[], char ResponseCode[], long 
NotificationMaxDelay, byte StatusFlags[], char 
Notification[], long EVSEProcessing, float 
NominalVoltage, float MaxCurrent )
```

## Description

Creates a Charge Parameter Discovery Response message for sending, using the AC syntax.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **NotificationMaxDelay**: Time until the vehicle is expected to react on the notification (for AC_EVSEStatus).
- **StatusFlags**: Flags for AC_EVSEStatus:
  - StatusFlags[0] = PowerSwitchClosed
  - StatusFlags[1] = RCD
- **Notification**: Notification about an action that the charge point wants the vehicle to perform (for AC_EVSEStatus).
- **EVSEProcessing**:
  - 0 if **Finished**
  - 1 if **Ongoing**
  - 2 if **Ongoing_WaitingForCustomerInteraction** (ISO 15118)
- **NominalVoltage**: Line voltage supported by the EVSE.
- **MaxCurrent**: EVSEMaxCurrent

### Optional Parameters

| Index | Name            | Type | Description                          |
|-------|-----------------|------|--------------------------------------|
| 0     | SAScheduleList  | long | Schedule / tariff list from secondary actor |

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—
