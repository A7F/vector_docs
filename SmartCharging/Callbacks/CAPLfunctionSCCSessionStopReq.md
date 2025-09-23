[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSessionStopReq.md)

# SCC_SessionStopReq

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_SessionStopReq

**Valid for**:  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_SessionStopReq ( byte SessionID[], long Terminate )
```

## Description

The callback is called as soon as a Session Stop Request is received.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF
- **Terminate**: 1 if charging status == terminate; for all other values: 0

## Return Values

—

## Example

—
