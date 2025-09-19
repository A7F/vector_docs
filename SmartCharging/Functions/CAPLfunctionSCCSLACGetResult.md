[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetResult.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Data Queries](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_GetResult

# SCC_SLAC_GetResult

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**

- This function can be called only within the assigned callback. The function is used to query the details of a request.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

`long SCC_SLAC_GetResult ( )`

## Description

Queries the result code (from different SLAC messages).

## Parameters

—

## Return Values

- **0x00**: Success
- **0x01-0xFF**: Reserved
- **0x00**: Not Ready
- **0x01**: Ready
- **0x02**: Success
- **0x03**: Failure
- **0x04**: Not Required
- **0x05-0xFF**: Reserved

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
