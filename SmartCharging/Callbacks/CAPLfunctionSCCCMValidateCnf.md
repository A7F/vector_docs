[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMValidateCnf.md)

## SCC_CM_Validate_Cnf

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_CM_Validate_Cnf

**Valid for**:  CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_CM_Validate_Cnf ( byte RunId[], byte SourceMacAddress[], dword Result, dword ToggleNum )
```

### Description

The callback is called as soon as a **CM_Validate.Cnf** message is received. Further details (signal type) that are transmitted in this request can be queried with [SCC_SLAC_GetSignalType](../Functions/CAPLfunctionSCCSLACGetSignalType.md).

### Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **Result**: The validation Result code according to the specification.
- **ToggleNum**: 0x00 in step 1, the number of BC-edges detected by the EVSE in step 2 of the validation process.

### Return Values

—

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)