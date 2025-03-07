[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCStartRenegotiation.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » SCC_StartRenegotiation

# SCC_StartRenegotiation

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SCC_StartRenegotiation ( )
```

## Description

Initiates a renegotiation procedure while inside the charge loop.

**Note**  
The charge point may initiate a renegotiation procedure by sending an **EVSENotification** with the value **ReNegotiation** (see [SCC_SetEVSENotification](CAPLfunctionSCCSetEVSENotification.md)).

## Parameters

—

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)