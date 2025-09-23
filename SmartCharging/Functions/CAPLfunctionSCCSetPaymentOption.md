[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetPaymentOption.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » SCC_SetPaymentOption

# SCC_SetPaymentOption

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```
long SCC_SetPaymentOption ( char PaymentOption[], dword Force )
```

## Description

Sets the desired payment option **for a running SCC session**.

## Parameters

- **PaymentOption**: Desired payment option as string. For ISO 15118, the value must be either **Contract** (indicates PnC mode) or **ExternalPayment** (indicates EIM mode).
- **Force**: If set to 1, the vehicle is forced to set the payment option even if the charge point hasn’t offered it previously. If set to 0, the payment option is only selected if it has been offered.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
