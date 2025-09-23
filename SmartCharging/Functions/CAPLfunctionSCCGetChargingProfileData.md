[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetChargingProfileData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEVSE) » **SCC_GetChargingProfileData**

# SCC_GetChargingProfileData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Note

- This function can be called only within the assigned callback. The function is used to query the details of a request.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```c
void SCC_GetChargingProfileData ( long Index, dword& Start, float& MaxPower, long& MaxNumberOfPhases )
```

## Description

Get the content of a charging profile within a **ChargeParameterDiscoveryReq** message.

## Parameters

- **Index**: Selected index of the target ChargingProfile (\<ChargingProfilesCount\>).
- **Start**: Gets the start time of the ChargingProfile (via reference).
- **MaxPower**: Gets the MaxPower of the ChargingProfile (via reference).
- **MaxNumberOfPhases**: Gets the MaxNumberOfPhases of the ChargingProfile (via reference).

## Return Values

—

## Example

—
