[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetChargeLoopInterval.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » SCC_SetChargeLoopInterval

# SCC_SetChargeLoopInterval

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_SetChargeLoopInterval ( dword Interval )
void SCC_SetChargeLoopInterval ( dword Interval, float jitterPercent )
```

## Description

Specifies the interval time between consecutive requests when inside the charge loop. Does not apply to **MeteringReceipt**.

## Parameters

- **Interval**: Desired interval time in milliseconds
- **JitterPercent**: Desired jitter (max. random variation) in % of Interval

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)