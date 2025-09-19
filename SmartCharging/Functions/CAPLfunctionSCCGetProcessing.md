[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetProcessing.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » **SCC_GetProcessing**

# SCC_GetProcessing

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**

- This function can be called only within the assigned callback. The function is used to query the details of a request.
- This function applies only to the SAScheduleList of ISO 15118
- `<InvalidValueSigned>` and / or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

`long SCC_GetProcessing ( )`

## Description

Gets the processing state.

## Parameters

—

## Return Values

- **0**: If **Finished**.
- **1**: If **Ongoing**.
- **2**: If **Ongoing_WaitingForCustomerInteraction** (ISO 15118).

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version **18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
