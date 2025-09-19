[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetRandomValue.md)

# SCC_SLAC_GetRandomValue

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Data Queries](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_GetRandomValue

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

`void SCC_SLAC_GetRandomValue ( byte Rnd[] )`

## Description

Gets the random value transmitted with **CM_MNBC_Sound.Ind**.

## Parameters

- **Rnd**: Queries the random value transmitted with **CM_MNBC_Sound.Ind** (16 byte) (to the given byte buffer).

## Return Values

—

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
