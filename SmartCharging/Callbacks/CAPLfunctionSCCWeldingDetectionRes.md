[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCWeldingDetectionRes.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » **SCC_WeldingDetectionRes**

# SCC_WeldingDetectionRes

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_WeldingDetectionRes ( byte SessionID[], long ResponseCode, float EVSEPresentVoltage )
```

## Description

The callback is called as soon as a Welding Detection Response is received. Further details that are transmitted in this request can be queried with the following function:

- [SCC_GetResponseCodeString](../Functions/CAPLfunctionSCCGetResponseCodeString.md)

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: 1 if **OK**, 0 if **FAILED**
- **EVSEPresentVoltage**: Current voltage value of charge point.

## Return Values

—

## Example

—
