# SCC_SetReceiptRequired

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetReceiptRequired.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetReceiptRequired

## Valid for:
- CANoe DE
- CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SetReceiptRequired ( long ReceiptRequired )
```

## Description

Sets the flag **ReceiptRequired**, and adapts the simulation state to await a **MeteringReceiptReq** next. Although **MeteringReceipt** is a specific message for PnC mode, this is also possible when using EIM mode.

## Parameters

- **ReceiptRequired**
  - 1 if a MeteringReceiptReq is expected next.
  - 0 if another ChargingStatusReq is expected.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
