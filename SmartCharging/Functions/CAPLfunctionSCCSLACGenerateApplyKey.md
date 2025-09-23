[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGenerateApplyKey.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Simulation](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_GenerateApplyKey

# SCC_SLAC_GenerateApplyKey

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```
long SCC_SLAC_GenerateApplyKey ( )
```

## Description

Immediately sends a **CM_Set_Key.Req** message with a new NMK and NID. If a NMK is defined in the XML configuration file, this NMK is permanently discarded.

## Parameters

—

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
