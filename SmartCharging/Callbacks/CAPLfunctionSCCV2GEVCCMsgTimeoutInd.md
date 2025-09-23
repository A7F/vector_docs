[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCV2GEVCCMsgTimeoutInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_V2G_EVCC_Msg_TimeoutInd

# SCC_V2G_EVCC_Msg_TimeoutInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```c
void SCC_V2G_EVCC_Msg_TimeoutInd 
( byte SessionID[], dword MessageID )
```

## Description

The callback is called as soon as an V2G_EVCC_Msg_Timeout occurs.

## Parameters

- **SessionID**: 8-byte long SessionID of the SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **[MessageID](SCC_MessageID.md)**: Type of message to be sent.

## Return Values

—

## Example

—
