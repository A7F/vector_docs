[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetSalesTariffData.md)

## SCC_GetSalesTariffData

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » SCC_GetSalesTariffData

**Valid for:** CANoe DE • CANoe4SW DE

### Note

- This function applies only to the SAScheduleList of ISO 15118.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

### Function Syntax

```plaintext
void SCC_GetSalesTariffData ( long Index, 
char IdAttr[], long& SalesTariffId, 
char Description[], long& NumEPriceLevels )
```

### Description

Gets various elements of the Sales Tariff within the **SAScheduleTuple** with the selected index.

### Parameters

- **Index**: Selected index of a SAScheduleTuple.
- **IdAttr**: Queries the Id attribute (to the given char buffer).
- **SalesTariffId**: Gets the SalesTariffId (via reference).
- **Description**: Queries the description (to the given char buffer).
- **NumEPriceLevels**: Gets number of distinct price levels of the SalesTariff (via reference).

### Return Values

—

### Example

—
