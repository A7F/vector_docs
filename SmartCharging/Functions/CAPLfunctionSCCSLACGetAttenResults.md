[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetAttenResults.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Data Queries](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_GetAttenResults

# SCC_SLAC_GetAttenResults

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**

- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_SLAC_GetAttenResults ( float Results[], long& ResultCount )
```

## Description

Gets the measured average attenuation values during the callback [SCC_SLACFinishedInd](../Callbacks/CAPLfunctionSCCSLACFinishedInd.md).

## Parameters

- **Results**: Queries the attenuation results (to the given float buffer). The results are returned sorted, starting with the lowest attenuation.
- **ResultCount**: Gets the number of results in the array (via reference).

## Return Values

—

## Example

—
