[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMSLACMatchCnf.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_CM_SLAC_Match_Cnf

# SCC_CM_SLAC_Match_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```c
void SCC_CM_SLAC_Match_Cnf ( byte RunId[], byte SourceMacAddress[], byte PEVMAC[], byte EVSEMAC[], byte NID[], byte NMK[] )
```

## Description

The callback is called as soon as a **CM_SLAC_Match.Cnf** message is received. Further details that are transmitted in this request can be queried with the following functions:

- [SCC_SLAC_GetApplicationType](../Functions/CAPLfunctionSCCSLACGetApplicationType.md)
- [SCC_SLAC_GetSecurityType](../Functions/CAPLfunctionSCCSLACGetSecurityType.md)
- [SCC_SLAC_GetMVFLength](../Functions/CAPLfunctionSCCSLACGetMVFLength.md)
- [SCC_SLAC_GetPEVAndEVSEId](../Functions/CAPLfunctionSCCSLACGetPEVAndEVSEId.md)

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **PEVMAC**: PEV MAC Address.
- **EVSEMAC**: EVSE MAC Address.
- **NID**: Network ID given by the CCo (EVSE).
- **NMK**: Private NMK of the EVSE (random value).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)