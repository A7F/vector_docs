[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetConsumptionCostData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » SCC_GetConsumptionCostData

# SCC_GetConsumptionCostData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Note
- This function applies only to the SAScheduleList of ISO 15118.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_GetConsumptionCostData ( long i1, long i2, long i3, float& StartValue, long& CostCount )
```

## Description

Gets the start value and the number of Cost subelements of the **ConsumptionCost** element with the selected indices.

## Parameters

- **i1**: Selected index of the target SAScheduleTuple.
- **i2**: Selected index of the target SalesTariffEntry.
- **i3**: Selected index of the target ConsumptionCost element.
- **StartValue**: Gets the start value of the selected ConsumptionCost element (via reference).
- **CostCount**: Gets the number of cost subelements of the selected ConsumptionCost element (via reference).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)