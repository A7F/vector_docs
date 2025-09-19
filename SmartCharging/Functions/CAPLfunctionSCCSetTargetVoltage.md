[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetTargetVoltage.md)

## SCC_SetTargetVoltage

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetTargetVoltage

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Note

This function needs a running SCC session in order to work. Make sure to call it only after the Session Setup Request message is sent.

### Function Syntax

```
long SCC_SetTargetVoltage ( float TargetVoltage )
```

### Description

Sets the desired voltage. These limits are used in various DC messages. If no values are set, the vehicle will automatically calculate defaults.

### Parameters

- **TargetVoltage**: Value to be set.

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—
