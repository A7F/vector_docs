[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetPMaxScheduleEntryData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » **SCC_GetPMaxScheduleEntryData**

# SCC_GetPMaxScheduleEntryData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- This function applies only to the SAScheduleList of ISO 15118.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_GetPMaxScheduleEntryData ( long i1, 
long i2, long& Start, long& Duration, 
float& PMax )
```

## Description

Gets various data of a **PMaxScheduleEntry**.

## Parameters

- **i1**: Selected index of the target SAScheduleTuple.
- **i2**: Selected index of the target PMaxScheduleEntry.
- **Start**: Gets the start time of the entry with the selected indices (via reference).
- **Duration**: Gets the duration of the entry with the selected indices (via reference). -1 is returned if not present.
- **PMax**: Gets the maximum power of the entry with the selected indices (via reference).

## Return Values

—

## Example

—

[SCC_GetPMaxScheduleID](CAPLfunctionSCCGetPMaxScheduleID.md) • [SCC_GetPMaxScheduleEntryCount](CAPLfunctionSCCGetPMaxScheduleEntryCount.md)
