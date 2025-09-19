[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetServiceIds.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » **SCC_GetServiceIds**

# SCC_GetServiceIds

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- This function can be called only within the assigned callback. The function is used to query the details of a request.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
long SCC_GetServiceIds(dword ChargeServiceIDs[], dword ServiceListIDs[], long& ChargeServiceIDsCount, long& ServiceListIDsCount);
```

## Description

Returns the **ServiceID** from the **ChargeService** and the **ServiceIDs** from the **ServiceList** sent with the current **ServiceDiscoveryRes** on EVSE side.

This function is meant to help with matching the **SerivceIDs** received from an EV against the information sent within a **ServiceDiscoveryRes** by the EVSE.

Note: This function is only valid during a `SCC_MessageTxInd()` callback with MessageID = 8 (ServiceDiscoveryRes).

## Parameters

- **ChargeServiceIDs**: The destination array of at least size 1 to receive the ServiceID from the ChargeService.
- **ServiceListIDs**: The destination array is large enough to receive the (maximum) number of expected ServiceIDs from the ServiceList as per your SCC_ChargePoint XML configuration file.
- **ChargeServiceIDsCount**:
  - In: dimension of the destination array
  - Out: The number of charge services
- **ServiceListIDsCount**:
  - In: dimension of the destination array
  - Out: The number of ServiceIDs returned in the ServiceListIDs array, may be 0 (zero) if no ServiceList is contained in the message.

## Return Values

- **0**: error, the message was called in the wrong V2G context, i.e., not during a SCC_MessageTxInd() with message = ServiceDiscoveryRes.
- **1**: success
- **2**: success, but the specified array dimension was too short. Increase the arrays dimension to receive all data.

## Example

—

[SCC_MessageTxInd](../Callbacks/CAPLfunctionSCCMessageTxInd.md) • [Message ID](../Callbacks/SCC_MessageID.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
