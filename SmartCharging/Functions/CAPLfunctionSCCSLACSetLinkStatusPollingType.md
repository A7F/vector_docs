[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACSetLinkStatusPollingType.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **SLAC Simulation** » **Shared Functions** » **SCC_SLAC_SetLinkStatusPollingType**

# SCC_SLAC_SetLinkStatusPollingType

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SCC_SLAC_SetLinkStatusPollingType ( dword Type )
```

**Note**  
It is recommended to use `VS_Host_Action.Ind` as described in [SCC_Generic_VS_HostMessage_Ind](../Callbacks/CAPLfunctionIndGenericVSHostMessageInd.md) instead of link status polling.

## Description

Changes the message(s) used for querying the link status (if activated). This overwrites the configuration parameter `<SLAC_LinkStatusPollingType>`.

## Parameters

- **Type**: Desired message configuration, where the following applies:
  - 0 = use both available messages
  - 1 = use only VS_PL_Lnk_Status
  - 2 = use only VS_Nw_Info

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
