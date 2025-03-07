[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreatePowerDeliveryReqDCDIN.md)

## SCC_CreatePowerDeliveryReqDC_DIN

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » SCC_CreatePowerDeliveryReqDC_DIN

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
long SCC_CreatePowerDeliveryReqDC_DIN 
( byte SessionID[], byte StatusFlags[], 
char ErrorCode[], long ReadyToChargeState, 
long ChargingComplete )
```

### Description

Creates a Power Delivery Request message for sending, using the DC syntax.

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **StatusFlags**: Flags for DC_EVStatus:
  - StatusFlags[0] = EVReady
  - StatusFlags[1] = EVCabinConditioning
  - StatusFlags[2] = EVRESSConditioning
  - StatusFlags[3] = EVRESSSOC
- **ErrorCode**: EVErrorCode for DC_EVStatus.
- **ReadyToChargeState**: 1 if start of charging is requested, 0 if stop of charging is requested.
- **ChargingComplete**: 1, if the battery is completely charged; otherwise 0.

#### Optional Parameters

- **Index 0**: ChargingProfile
  - **Type**: complex
  - **Description**: Desired charging profile for the current charging session (i.e. maximum amount of power drawn over time).
- **Index 1**: BulkChargingComplete
  - **Type**: long
  - **Description**: 1, if the bulk charging operation is complete; otherwise 0.

### Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)