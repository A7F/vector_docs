[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetNotificationMaxDelay.md)

# SCC_SetNotificationMaxDelay

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetNotificationMaxDelay

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SetNotificationMaxDelay(long MaxDelay)
```

## Description

Sets the maximally allowed delay time for the vehicle to react on the provided notification.

## Parameters

- **MaxDelay**: Target delay time.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—