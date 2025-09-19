[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateChargeParameterDiscoveryReqDCDin.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » SCC_CreateChargeParameterDiscoveryReqDC_DIN

# SCC_CreateChargeParameterDiscoveryReqDC_DIN

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateChargeParameterDiscoveryReqDC_DIN 
( byte SessionID[], byte StatusFlags[], 
char ErrorCode[], char EnergyTransferType[], 
float MaxCurrent, float MaxVoltage)
```

## Description

Creates a Charge Parameter Discovery Request message for sending, using the DC syntax.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **StatusFlags**: Flags for DC_EVStatus:
  - StatusFlags[0] = EVReady
  - StatusFlags[1] = EVCabinConditioning
  - StatusFlags[2] = EVRESSConditioning
  - StatusFlags[3] = EVRESSSOC
- **ErrorCode**: EVErrorCode for DC_EVStatus.
- **EnergyTransferType**: Desired charging mode.
- **MaxCurrent**: EVMaxCurrent
- **MaxVoltage**: EVMaxVoltage

### Optional Parameters

- **Index 0**: MaxPower (float) - EVMaximumPowerLimit
- **Index 1**: EnergyCapacity (float) - Maximum supported power capacity in Wh.
- **Index 2**: EnergyRequest (float) - Amount of requested energy in Wh.
- **Index 3**: FullSOC (long) - Charge percentage to be considered as fully charged.
- **Index 4**: BulkSOC (long) - Charge percentage to be considered as the end of a fast charge process.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
