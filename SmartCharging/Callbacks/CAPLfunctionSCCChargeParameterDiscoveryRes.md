[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCChargeParameterDiscoveryRes.md)

## SCC_ChargeParameterDiscoveryRes

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_ChargeParameterDiscoveryRes

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_ChargeParameterDiscoveryRes 
( byte SessionID[], long ResponseCode, 
long SAScheduleTupleCount )
```

### Description
The callback is called as soon as a Charge Parameter Discovery Response is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetMaxVoltage](../Functions/CAPLfunctionSCCGetMaxVoltage.md)
- [SCC_GetMaxCurrent](../Functions/CAPLfunctionSCCGetMaxCurrent.md)
- [SCC_GetMinCurrent](../Functions/CAPLfunctionSCCGetMinCurrent.md)
- [SCC_GetSAScheduleTupleID](../Functions/CAPLfunctionSCCGetSAScheduleTupleID.md)
- [SCC_GetProcessing](../Functions/CAPLfunctionSCCGetProcessing.md)
- [SCC_GetMaxPower](../Functions/CAPLfunctionSCCGetMaxPower.md) (DC)
- [SCC_GetCurrentRegulationTolerance](../Functions/CAPLfunctionSCCGetCurrentRegulationTolerance.md) (DC)
- [SCC_GetEnergyToBeDelivered](../Functions/CAPLfunctionSCCGetEnergyToBeDelivered.md) (DC)
- [SCC_GetPeakCurrentRipple](../Functions/CAPLfunctionSCCGetPeakCurrentRipple.md) (DC)
- [SCC_GetMinVoltage](../Functions/CAPLfunctionSCCGetMinVoltage.md) (DC)
- [SCC_GetNominalVoltage](../Functions/CAPLfunctionSCCGetNominalVoltage.md) (ISO 15118 AC)
- [SCC_GetResponseCodeString](../Functions/CAPLfunctionSCCGetResponseCodeString.md)

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: 1 if **OK**, 0 if **FAILED**
- **SAScheduleTupleCount**: Number of transmitted tuples

### Return Values
—

### Example
—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
