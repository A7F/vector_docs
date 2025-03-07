[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetPresentVoltage.md)

## SCC_SetPresentVoltage

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetPresentVoltage

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
long SCC_SetPresentVoltage ( float PresentVoltage )
```

### Description

Sets the current voltage output. This value is used in various DC messages, and for calculating the MeterInfo in AC mode. If no value is set, the charge point will automatically calculate a default.

### Parameters

- **PresentVoltage**: Value to be set.

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—