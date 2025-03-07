[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetPeakCurrentRipple.md)

# SCC_SetPeakCurrentRipple

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetPeakCurrentRipple

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SetPeakCurrentRipple ( float PeakCurrentRipple )
```

## Description

This function sets the EVSEPeakCurrentRipple of DC_EVSEChargeParameter.

## Parameters

- **PeakCurrentRipple**: Nominal voltage of EVSE [A].

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—