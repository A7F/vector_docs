[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCShutdown.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » **SCC_Shutdown**

# SCC_Shutdown

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```
long SCC_Shutdown ( long Terminate )
```

## Description

Stops the charging session when inside the charge loop, by starting a regular shutdown procedure.

## Parameters

- **Terminate**: If 1, the **SessionStopReq** is sent with **ChargingSession** = **Terminate**, else with **ChargingSession** = **Pause** (ISO 15118 only, else this value is ignored).

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)