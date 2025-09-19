[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionCreateGenericVSVersionQueryReq.md)

## SCC_CreateGenericVS_VersionQuery_Req

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Test Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » SCC_CreateGenericVS_VersionQuery_Req

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
long SCC_CreateGenericVS_VersionQuery_Req(byte SourceMac[], byte TargetMac[], byte OUI[]);
```

### Description

Creates a `VS_Get_Version.Req` or equivalent message depending on the provided vendor OUI. The vendor OUI can be queried with the function [SCC_SLAC_GetOUI](CAPLfunctionSCCSLACGetOUI.md). The respective confirmation message will trigger the [SCC_Generic_VS_VersionQuery_Cnf](../Callbacks/CAPLfunctionIndGenericVSHostMessageInd.md) callback.

Currently supported OUIs:

- Qualcomm (0x00B052)
- MStar, MediaTek and Vertexcom (0x0013D7)
- Lumissil (0x0016E8)

### Parameters

- **SourceMac**: MAC address of the sender.
- **TargetMac**: MAC address of the receiver.
- **OUI**: Vendor OUI of the chip, used to create the correct message for this type of chip.

### Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
