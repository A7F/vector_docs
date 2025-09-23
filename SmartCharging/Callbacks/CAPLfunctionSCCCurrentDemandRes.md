[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCurrentDemandRes.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **EV Callback Functions** » **SCC_CurrentDemandRes**

# SCC_CurrentDemandRes

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_CurrentDemandRes ( byte SessionId[], long ResponseCode, float EVSEPresentVoltage, float EVSEPresentCurrent, byte LimitAchievedFlags[], char EVSEID[], long SAScheduleTupleID, long ReceiptRequired)
```

## Description

The callback is called as soon as a Current Demand Response is received. Further details that are transmitted in this message can be queried with the following functions:

- [SCC_GetMaxPower](../Functions/CAPLfunctionSCCGetMaxPower.md)
- [SCC_GetMaxVoltage](../Functions/CAPLfunctionSCCGetMaxVoltage.md)
- [SCC_GetMaxCurrent](../Functions/CAPLfunctionSCCGetMaxCurrent.md)
- [SCC_GetMeterInfoData](../Functions/CAPLfunctionSCCGetMeterInfoData.md) (ISO 15118)
- [SCC_GetResponseCodeString](../Functions/CAPLfunctionSCCGetResponseCodeString.md)

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: 1 if **OK**, 0 if **FAILED**
- **EVSEPresentVoltage**: Present voltage value of charge point.
- **EVSEPresentCurrent**: Present current of charge point.
- **LimitAchievedFlags (ISO 15118)**: Array of three flags which correspond to current | voltage | power limit achieved, in this order.
- **EVSEID (ISO 15118)**: ID of charge point.
- **SAScheduleTupleID (ISO 15118)**: ID of the selected SAScheduleTuple.
- **ReceiptRequired (ISO 15118)**: Indicates if the vehicle is required to send a MeteringReceiptReq.

## Return Values

—

## Example

—
