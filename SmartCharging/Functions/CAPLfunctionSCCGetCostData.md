[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetCostData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » **SCC_GetCostData**

# SCC_GetCostData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**

- This function applies only to the SAScheduleList of ISO 15118.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_GetCostData ( long i1, long i2, long i3, 
long i4, char CostKind[], dword& Amount, 
long& AmountMultiplier, long& HasMultiplier )
```

## Description

Gets the kind, amount and multiplier (range [-3..3]) values of the **Cost** element with the selected indices.

## Parameters

- **i1**: Selected index of the target SAScheduleTuple.
- **i2**: Selected index of the target SalesTariffEntry.
- **i3**: Selected index of the target ConsumptionCost element.
- **i4**: Selected index of the target Cost element.
- **CostKind**: Queries the kind of the Cost element with the selected indices (to the given char buffer).
- **Amount**: Gets the amount of the Cost element with the selected indices (via reference).
- **Multiplier**: Gets the Multiplier (range [-3..3]) value of the Cost element with the selected indices (via reference).
- **HasMultiplier**: Gets the HasMultiplier flag that is set to 0 to denote that the multiplier is not present (via reference).

## Return Values

—

## Example

—

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
