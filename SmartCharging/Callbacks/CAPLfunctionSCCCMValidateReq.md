[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMValidateReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_CM_Validate_Req

# SCC_CM_Validate_Req

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CM_Validate_Req ( byte RunId[], byte SourceMacAddress[], dword ListenTimer )
```

## Description

The callback is called as soon as a **CM_Validate.Req** message is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_SLAC_GetSignalType](../Functions/CAPLfunctionSCCSLACGetSignalType.md)
- [SCC_SLAC_GetResult](../Functions/CAPLfunctionSCCSLACGetResult.md)

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **ListenTimer**: Time duration while the EVSE shall listen to BCB-toggles:
  - 0x00 = 100 ms
  - 0x01 = 200 ms

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
