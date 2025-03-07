[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMAttenCharRsp.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_CM_Atten_Char_Rsp

# SCC_CM_Atten_Char_Rsp

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CM_Atten_Char_Rsp ( byte RunId[], byte SourceMacAddress[], byte SourceAddress[] )
```

## Description

The callback is called as soon as a **CM_Atten_Char.Rsp** message is received.

- [SCC_SLAC_GetApplicationType](../Functions/CAPLfunctionSCCSLACGetApplicationType.md)
- [SCC_SLAC_GetSecurityType](../Functions/CAPLfunctionSCCSLACGetSecurityType.md)
- [SCC_SLAC_GetSourceId](../Functions/CAPLfunctionSCCSLACGetSourceId.md)
- [SCC_SLAC_GetResponseId](../Functions/CAPLfunctionSCCSLACGetResponseId.md)
- [SCC_SLAC_GetResult](../Functions/CAPLfunctionSCCSLACGetResult.md)

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **SourceAddress**: MAC Address of the vehicle which initiates the SLAC process.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)