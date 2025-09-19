[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCVSPLLnkStatusCnf.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_VS_PL_Lnk_Status_Cnf

# SCC_VS_PL_Lnk_Status_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```
void SCC_VS_PL_Lnk_Status_Cnf ( byte SourceMacAddress[], dword MStatus, dword LinkStatus )
```

## Description

The callback is called as soon as a **VS_PL_Lnk_Status.Cnf** message is received. This is the response of the QCA7000 chip when using link status polling. (Additional data cannot be queried at the moment.)

## Parameters

- **SourceMacAddress**: MAC address of sender.
- **MStatus**: MStatus code:
  - 0x00 = success
  - 0x01 = failure
- **LinkStatus**: Notification if the link is established:
  - 0x00 = no link
  - 0x01 = link

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
