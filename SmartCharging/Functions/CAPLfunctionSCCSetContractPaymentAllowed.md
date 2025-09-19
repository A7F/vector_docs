[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetContractPaymentAllowed.md)

# SCC_SetContractPaymentAllowed

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControlEVSE) » SCC_SetContractPaymentAllowed

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SetContractPaymentAllowed ( dword Allowed )
```

## Description

Changes the available **PaymentOptions** to be sent in the **ServiceDiscovery** response message.

## Parameters

- **Allowed**: 1 to allow the PaymentOption, 0 to disallow. The other option will automatically be activated if an option is disallowed.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
