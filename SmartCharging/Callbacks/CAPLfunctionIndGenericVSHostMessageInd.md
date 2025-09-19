[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionIndGenericVSHostMessageInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_Generic_VS_HostMessage_Ind

# SCC_Generic_VS_HostMessage_Ind

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_Generic_VS_HostMessage_Ind(byte sourceMacAddress[], dword hostMessageInd);
```

## Description

The callback is called as soon as a [VS_Host_Action.Ind](CAPLfunctionSCCVSHostActionInd.md) or equivalent message is received. The interpretation of the message depends on the vendor OUI and will then be mapped to the respective `hostMessageInd` values.

Currently supported OUIs:

- Qualcomm (0x00B052)
- MStar, MediaTek and Vertexcom (0x0013D7)
- Lumissil (0x0016E8)

## Parameters

- **SourceMacAddress**: MAC address of sender.
- **hostMessageInd**: Notification:
  - DEVICE_READY = 0x00
  - READY_TO_JOIN = 0x01
  - AVLN_JOINED = 0x02
  - AVLN_DISCONNECTED = 0x03
  - NOT_SUPPORTED = 0xFF

## Return Values

—

## Example

—

[SCC_VS_HostAction_Ind](CAPLfunctionSCCVSHostActionInd.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
