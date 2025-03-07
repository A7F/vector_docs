[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMAttenCharInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_CM_Atten_Char_Ind

# SCC_CM_Atten_Char_Ind

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void SCC_CM_Atten_Char_Ind ( byte RunId[], byte SourceMacAddress[], byte SourceAddress[], dword NumSounds, dword NumGroups, byte AAG[] )
```

## Description

The callback is called as soon as a **CM_Atten_Char.Ind** message is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_SLAC_GetApplicationType](../Functions/CAPLfunctionSCCSLACGetApplicationType.md)
- [SCC_SLAC_GetSecurityType](../Functions/CAPLfunctionSCCSLACGetSecurityType.md)
- [SCC_SLAC_GetSourceId](../Functions/CAPLfunctionSCCSLACGetSourceId.md)
- [SCC_SLAC_GetResponseId](../Functions/CAPLfunctionSCCSLACGetResponseId.md)

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **SourceAddress**: MAC Address of the EV which initiates the SLAC process.
- **NumSounds**: Number of M-Sounds used to generate the ATTEN_PROFILE.
- **NumGroups**: Number of attenuation groups.
- **AAG**: Average Attenuation Group (array length is indicated by the parameter **NumGroups**).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)