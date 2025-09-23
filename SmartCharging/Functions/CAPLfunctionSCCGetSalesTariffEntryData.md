# SCC_GetSalesTariffEntryData

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetSalesTariffEntryData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » SCC_GetSalesTariffEntryData

**Valid for**: CANoe DE • CANoe4SW DE

## Note

- This function applies only to the SAScheduleList of ISO 15118.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_GetSalesTariffEntryData ( 
long i1, long i2, long& Start, long& Duration, 
long& EPriceLevel, long& ConsumptionCostCount )
```

## Description

Gets the start time, duration, price level and the number of **ConsumptionCost** subelements of the **SalesTariffEntry** with the selected indices.

## Parameters

- **i1**: Selected index of the target SAScheduleTuple (< TariffCount).
- **i2**: Selected index of the target SalesTariffEntry (< SalesTariffEntriesCount).
- **Start**: Gets the start time of the entry with the selected indices (via reference).
- **Duration**: Gets the duration of the entry with the selected indices (via reference).
- **EPriceLevel**: Gets the EPriceLevel of the entry with the selected indices (-1 is returned if not present) (via reference).
- **ConsumptionCostCount**: Gets the number of ConsumptionCost subelements of the SalesTariffEntry with the selected indices (via reference).

## Return Values

—

## Example

—
