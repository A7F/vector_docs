[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetSalesTariffEntryCount.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » **SCC_GetSalesTariffEntryCount**

# SCC_GetSalesTariffEntryCount

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**

- This function applies only to the SAScheduleList of ISO 15118.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
long SCC_GetSalesTariffEntryCount ( long Index )
```

## Description

Gets the number of **SalesTariffEntries** in the **SalesTariff** within the **SAScheduleTuple** with the selected index.

## Parameters

- **Index**: Selected index of the target SAScheduleTuple (< TariffCount).

## Return Values

The number of **SalesTariffEntries** in the **SalesTariff** within the **SAScheduleTuple** with the selected index.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)