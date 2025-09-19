[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCLinkStatusChangeInd.md)

# SCC_LinkStatusChangeInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_LinkStatusChangeInd

Valid for:  CANoe DE • CANoe4SW DE

**Note:** The link status can also be changed manually using [SCC_SLAC_SetLinkStatus](../Functions/CAPLfunctionSCCSLACSetLinkStatus.md).

## Function Syntax

```plaintext
void SCC_LinkStatusChangeInd ( dword OldStatus, dword NewStatus )
```

## Description

The callback is called each time the internally stored link status changes.

To use this callback, the XML-parameter `<SLAC_ChipMACAddress>` must either be set to the correct value or removed. Otherwise, the polling message is ignored.

**Note:** It is recommended to use **VS_Host_Action.Ind** as described in [SCC_Generic_VS_HostMessage_Ind](CAPLfunctionIndGenericVSHostMessageInd.md) instead of link status polling.

## Parameters

- **OldStatus**: Previous link status (0 = no link, 1 = link, 2 = unknown).
- **NewStatus**: New link status (0 = no link, 1 = link, 2 = unknown).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
