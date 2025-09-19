[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateChargeParameterDiscoveryReqDCIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateChargeParameterDiscoveryReqDC_ISO**

# SCC_CreateChargeParameterDiscoveryReqDC_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateChargeParameterDiscoveryReqDC_ISO ( byte SessionID[], byte StatusFlags[], char ErrorCode[], char EnergyTransferType[], float MaxCurrent, float MaxVoltage)
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

1. **MaxPower**: `float` - EVMaximumPowerLimit
2. **EnergyCapacity**: `float` - Maximum supported power capacity in Wh.
3. **EnergyRequest**: `float` - Amount of requested energy in Wh.
4. **FullSOC**: `long` - Charge percentage to be considered as fully charged.
5. **BulkSOC**: `long` - Charge percentage to be considered as the end of a fast charge process.
6. **MaxEntriesSAScheduleTuple**: `long` - Maximal number of entries in the SAScheduleTuple.
7. **DepartureTime**: `dword` - Intended time to finish the charging process, in "seconds from now".

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
