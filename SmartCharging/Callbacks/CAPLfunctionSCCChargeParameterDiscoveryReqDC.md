[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCChargeParameterDiscoveryReqDC.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **EVSE Callback Functions** » **SCC_ChargeParameterDiscoveryReqDC**

# SCC_ChargeParameterDiscoveryReqDC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_ChargeParameterDiscoveryReqDC 
( byte SessionId[], double EVEnergyCapacity, 
double EVEnergyRequest)
```

## Description

The callback is called as soon as a Charge Parameter Discovery Request is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetEnergyTransferType](../Functions/CAPLfunctionSCCGetEnergyTransferType.md)
- [SCC_GetDepartureTime](../Functions/CAPLfunctionSCCGetDepartureTime.md)
- [SCC_GetMaxVoltage](../Functions/CAPLfunctionSCCGetMaxVoltage.md)
- [SCC_GetMaxCurrent](../Functions/CAPLfunctionSCCGetMaxCurrent.md)
- [SCC_GetMinCurrent](../Functions/CAPLfunctionSCCGetMinCurrent.md) (AC)
- [SCC_GetMaxPower](../Functions/CAPLfunctionSCCGetMaxPower.md) (DC)
- [SCC_GetFullSOC](../Functions/CAPLfunctionSCCGetFullSOC.md) (DC)
- [SCC_GetBulkSOC](../Functions/CAPLfunctionSCCGetBulkSOC.md) (DC)
- [SCC_GetMaxEntriesSAScheduleTuple](../Functions/CAPLfunctionSCCGetMaxEntriesSAScheduleTuple.md) (ISO 15118)
- [GetDC_EVStatus](../Functions/CAPLfunctionSCCGetDCEVStatus.md)

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **EVEnergyCapacity (DC)**: Maximum supported power.
- **EVEnergyRequest (DC)**: Energy required by the vehicle.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
