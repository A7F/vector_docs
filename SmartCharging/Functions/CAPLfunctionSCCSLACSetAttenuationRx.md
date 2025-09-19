[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACSetAttenuationRx.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Simulation](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_SetAttenuationRx

# SCC_SLAC_SetAttenuationRx

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SLAC_SetAttenuationRx ( float AttenuationRx )
```

## Description

Sets the attenuation of the Rx path, which is subtracted from the AAG values. This can also be used to influence the calculation of attenuation values when a real chip is used, i.e., the attenuation may be artificially raised or lowered.

## Parameters

- **AttenuationRx**: Attenuation value.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
