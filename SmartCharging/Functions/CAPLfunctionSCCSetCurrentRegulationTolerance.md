[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetCurrentRegulationTolerance.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetCurrentRegulationTolerance

# SCC_SetCurrentRegulationTolerance

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SetCurrentRegulationTolerance 
( float CurrentRegulationTolerance )
```

## Description

This function sets the EVSECurrentRegulationTolerance.

## Parameters

- **CurrentRegulationTolerance**: Value to set for EVSECurrentRegulationTolerance parameter of the ChargeParameterDiscoveryRes.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—