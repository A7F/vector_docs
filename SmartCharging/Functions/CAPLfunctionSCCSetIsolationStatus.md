[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetIsolationStatus.md)

## SCC_SetIsolationStatus

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetIsolationStatus

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
long SCC_SetIsolationStatus ( char IsolationStatus[] )
```

### Description

Sets the isolation status enum.

### Parameters

- **IsolationStatus**: String buffer that is written to the isolation status. The string should be a valid enum value according to the schema.

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—
