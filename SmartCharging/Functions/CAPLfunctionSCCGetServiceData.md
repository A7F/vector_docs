[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetServiceData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » **SCC_GetServiceData**

# SCC_GetServiceData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**

- This function can be called only within the assigned callback. The function is used to query the details of a request.
- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
  - These are returned if an optional numeric message parameter was queried by this function but not found.
  - See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_GetServiceData ( long Index, long& ServiceID, char ServiceName[], char ServiceType[], char ServiceScope[], long& FreeService )
```

## Description

Get various elements of a service within a ServiceDiscoveryRes message.

## Parameters

- **Index**: Selected index of a Service. When using a recent protocol version, an index of 0 refers to the element ChargeService.
- **ServiceID**: Gets the ServiceID (via reference).
- **ServiceName**: Queries the service name as string with 64 characters (to the given char buffer).
- **ServiceType**: Queries the service type (to the given char buffer).
- **ServiceScope**: Queries the service scope as string with 32 characters (to the given char buffer).
- **FreeService**: Gets the FreeService flag (via reference).

## Return Values

—

## Example

—
