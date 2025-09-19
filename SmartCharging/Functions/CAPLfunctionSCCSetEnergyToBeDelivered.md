[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetEnergyToBeDelivered.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » **SCC_SetEnergyToBeDelivered**

# SCC_SetEnergyToBeDelivered

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SetEnergyToBeDelivered ( float EnergyToBeDelivered )
```

## Description

Sets the target energy value, which is sent in the **ChargeParameterDiscoveryRes** message.

## Parameters

- **EnergyToBeDelivered**: Value to be set.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
