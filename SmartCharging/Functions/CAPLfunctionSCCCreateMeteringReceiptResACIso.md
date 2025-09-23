[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateMeteringReceiptResACIso.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateMeteringReceiptResAC_ISO**

# SCC_CreateMeteringReceiptResAC_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateMeteringReceiptResAC_ISO ( byte SessionID[], char ResponseCode[], long NotificationMaxDelay, byte StatusFlags[], char Notification[] )
```

## Description

Creates a Metering Receipt Response message for sending, using the AC syntax.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).
- **NotificationMaxDelay**: Time until the vehicle is expected to react on the notification (for AC_EVSEStatus).
- **StatusFlags**: Flags for AC_EVSEStatus:
  - StatusFlags[0] = PowerSwitchClosed
  - StatusFlags[1] = RCD
- **Notification**: Notification about an action that the charge point wants the vehicle to perform (for AC_EVSEStatus).

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—
