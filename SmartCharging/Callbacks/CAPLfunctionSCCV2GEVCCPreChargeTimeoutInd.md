[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCV2GEVCCPreChargeTimeoutInd.md)

# SCC_V2G_EVCC_PreCharge_TimeoutInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_V2G_EVCC_PreCharge_TimeoutInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_V2G_EVCC_PreCharge_TimeoutInd ( byte SessionID )
```

## Description

The callback is called as soon as an V2G_EVCC_PreCharge_Timeout occurs.

## Parameters

- **SessionID**: 8-byte long SessionID of the SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)