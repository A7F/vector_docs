[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCurrentDemandReq.md)

**CAPL Functions » Smart Charging » SCC Modeling Libraries (Simulation Setup) » EVSE Callback Functions » SCC_CurrentDemandReq**

# SCC_CurrentDemandReq

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Note

- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_CurrentDemandReq ( byte SessionID[], float TargetVoltage, float TargetCurrent)
```

## Description

The callback is called as soon as a Current Demand Request is received. Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetMaxVoltage](../Functions/CAPLfunctionSCCGetMaxVoltage.md)
- [SCC_GetMaxCurrent](../Functions/CAPLfunctionSCCGetMaxCurrent.md)
- [SCC_GetMaxPower](../Functions/CAPLfunctionSCCGetMaxPower.md)
- [SCC_GetBulkChargingComplete](../Functions/CAPLfunctionSCCGetBulkChargingComplete.md)
- [SCC_GetChargingComplete](../Functions/CAPLfunctionSCCGetChargingComplete.md)
- [SCC_GetRemainingTimeToFullSoC](../Functions/CAPLfunctionSCCGetRemainingTimeToFullSoC.md)
- [SCC_GetRemainingTimeToBulkSoC](../Functions/CAPLfunctionSCCGetRemainingTimeToBulkSoC.md)

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF
- **TargetVoltage**: Voltage demand
- **TargetCurrent**: Current demand

## Return Values

—

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
