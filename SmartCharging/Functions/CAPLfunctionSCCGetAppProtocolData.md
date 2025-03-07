[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetAppProtocolData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEVSE) » **SCC_GetAppProtocolData**

# SCC_GetAppProtocolData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**

- This function can be called only within the assigned callback. The function is used to query the details of a request.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_GetAppProtocolData ( long Index, 
char ProtocolNamespace[], long& VersionMajor, 
long& VersionMinor, long& SchemaID, 
long& Priority )
```

## Description

Gets the content of an AppProtocol element of a **SupportedAppProtocolReq** message.

## Parameters

- **Index**: Selected index of protocol list.
- **ProtocolNamespace**: Queries the protocol namespace as string with 100 characters (to the given char buffer).
- **VersionMajor**: Gets the major version (via reference).
- **VersionMinor**: Gets the minor version (via reference).
- **SchemaID**: Gets the schema id (via reference).
- **Priority**: Gets the Priority (via reference).

## Return Values

—

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)