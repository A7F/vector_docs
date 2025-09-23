[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetReservedField.md)

### SCC_SLAC_GetReservedField

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Data Queries](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_GetReservedField

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

**Note**

- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

### Function Syntax

```plaintext
long SCC_SLAC_GetReservedField ( dword Index, byte Data[], dword& DataSize )
```

### Description

Gets one of the reserved fields of the message. For a valid message, these fields must contain only zeroes.

### Parameters

- **Index**: Number of the reserved field (0 or 1).
- **Data**: Queries the field (to the given byte buffer).
- **DataSize**: Gets the byte length of the returned data (via reference).

### Return Values

- **0**: If the field could not be retrieved.
- **1**: otherwise

### Example

—
