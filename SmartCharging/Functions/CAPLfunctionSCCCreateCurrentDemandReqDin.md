[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCurrentDemandReqDin.md)

## SCC_CreateCurrentDemandReq_DIN

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » SCC_CreateCurrentDemandReq_DIN

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
long SCC_CreateCurrentDemandReq_DIN 
( byte SessionID[], byte StatusFlags[], 
char ErrorCode[], float TargetVoltage, 
float TargetCurrent, long ChargingComplete )
```

### Description

Creates a Current Demand Request message for sending.

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection range: 0 - 0xFF FF FF FF FF FF FF FF.
- **StatusFlags**: Flags for DC_EVStatus:
  - StatusFlags[0] = EVReady
  - StatusFlags[1] = EVCabinConditioning
  - StatusFlags[2] = EVRESSConditioning
  - StatusFlags[3] = EVRESSSOC
- **ErrorCode**: EVErrorCode for DC_EVStatus.
- **TargetVoltage**: EVTargetVoltage.
- **TargetCurrent**: EVTargetCurrent.
- **ChargingComplete**: 1, if the battery is completely charged; otherwise 0.

#### Optional Parameters

1. **MaxVoltage**: float - EVMaximumVoltageLimit
2. **MaxCurrent**: float - EVMaximumCurrentLimit
3. **MaxPower**: float - EVMaximumPowerLimit
4. **BulkChargingComplete**: long - 1, if the bulk charging operation is complete; otherwise 0.
5. **RemainingTimeToFullSOC**: float - Remaining time until full charging condition in seconds.
6. **RemainingTimeToBulkSOC**: float - Remaining time until bulk charging condition in seconds.

### Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)