[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetNominalVoltage.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetNominalVoltage

# SCC_SetNominalVoltage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SCC_SetNominalVoltage 
( float NominalVoltage )
```

## Description

This function sets the EVSENominalVoltage of AC_EVSEChargeParameter.

## Parameters

- **NominalVoltage**: Nominal voltage of EVSE [V]

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—