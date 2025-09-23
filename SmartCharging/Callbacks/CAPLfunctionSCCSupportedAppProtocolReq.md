[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSupportedAppProtocolReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_SupportedAppProtocolReq

# SCC_SupportedAppProtocolReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_SupportedAppProtocolReq ( dword AppProtocolCount )
```

## Description

The callback is called as soon as a **SupportedAppProtocol** Request is received.

The list entries must be queried via the separate help function [SCC_GetAppProtocolData](../Functions/CAPLfunctionSCCGetAppProtocolData.md).

## Parameters

- **AppProtocolCount**: Number of transmitted AppProtocol elements.

## Return Values

—

## Example

—
