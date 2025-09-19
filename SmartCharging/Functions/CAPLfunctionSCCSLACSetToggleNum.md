[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACSetToggleNum.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Simulation](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_SetToggleNum

# SCC_SLAC_SetToggleNum

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
long SCC_SLAC_SetToggleNum ( int ToggleNum )
```

## Description

Sets the number of toggles for the next **CM_Validate.Cnf** message. If this function is not used, either the value from the XML configuration or the default (2) is used.

**Note:** The number of toggles is only applied to the second **CM_Validate.Cnf** in a validation sequence. The first one is specified to always have ToggleNum = 0.

## Parameters

- **ToggleNum**: Number of received toggles (max. 255). Real systems use toggle numbers <= 3.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
