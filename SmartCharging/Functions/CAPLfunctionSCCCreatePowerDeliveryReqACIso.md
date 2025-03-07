[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreatePowerDeliveryReqACIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » SCC_CreatePowerDeliveryReqAC_ISO

# SCC_CreatePowerDeliveryReqAC_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreatePowerDeliveryReqAC_ISO 
( byte SessionID[], char ChargeProgress[], 
long SAScheduleTupleId )
```

## Description

Creates a Power Delivery Request message for sending, using the AC syntax.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ChargeProgress**: Type of action: "Start", "Stop" or "Renegotiate".
- **SAScheduleTupleId**: Unique ID of a SAScheduleTuple which identifies the selected Tariff.

### Optional Parameters

- **Index**: 0
- **Name**: ChargingProfile
- **Type**: complex
- **Description**: Desired charging profile for the current charging session (i.e. maximum amount of power drawn over time).

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)