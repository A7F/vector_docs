[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCStartCertificateUpdate.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » **SCC_StartCertificateUpdate**

# SCC_StartCertificateUpdate

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```
long SCC_StartCertificateUpdate ( )
```

## Description

Schedules a **CertificateUpdateReq** message to be sent after the **ServiceAndPaymentSelectioReq**. This is only possible when in ISO 15118 PnC mode.

## Parameters

—

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
