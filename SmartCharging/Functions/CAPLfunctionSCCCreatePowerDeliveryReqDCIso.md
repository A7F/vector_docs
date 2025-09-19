[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreatePowerDeliveryReqDCIso.md)

# SCC_CreatePowerDeliveryReqDC_ISO

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » SCC_CreatePowerDeliveryReqDC_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```
long SCC_CreatePowerDeliveryReqDC_ISO 
( byte SessionID[], byte StatusFlags[], 
char ErrorCode[], char ChargeProgress[], 
long SAScheduleTupleId, long ChargingComplete )
```

## Description

Creates a Power Delivery Request message for sending, using the DC syntax.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **StatusFlags**: Flags for DC_EVStatus:
  - StatusFlags[0] = EVReady
  - StatusFlags[1] = EVCabinConditioning
  - StatusFlags[2] = EVRESSConditioning
  - StatusFlags[3] = EVRESSSOC
- **ErrorCode**: EVErrorCode for DC_EVStatus.
- **ChargeProgress**: Type of action: "Start", "Stop" or "Renegotiate".
- **SAScheduleTupleId**: Unique ID of a SAScheduleTuple which identifies the selected Tariff.
- **ChargingComplete**: 1, if the battery is completely charged; otherwise 0.

### Optional Parameters

- **Index 0**: ChargingProfile
  - **Type**: complex
  - **Description**: Desired charging profile for the current charging session (i.e. maximum amount of power drawn over time).
- **Index 1**: BulkChargingComplete
  - **Type**: long
  - **Description**: 1, if the bulk charging operation is complete; otherwise 0.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
