[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACSetLinkStatusPollingInterval.md)

## SCC_SLAC_SetLinkStatusPollingInterval

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Simulation](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_SetLinkStatusPollingInterval

**Valid for**:  CANoe DE • CANoe4SW DE

### Function Syntax

```
long SCC_SLAC_SetLinkStatusPollingInterval ( long Interval )
```

### Description

This function changes the polling interval for sending **VS_PL_Lnk_Status** or **VS_Nw_Info** requests to the chip. Set the interval to 0 to disable polling.

**Note**: It is recommended to use `VS_Host_Action.Ind` as described in [SCC_Generic_VS_HostMessage_Ind](../Callbacks/CAPLfunctionIndGenericVSHostMessageInd.md) instead of link status polling.

### Parameters

- **Interval**: Desired time interval in milliseconds.

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—