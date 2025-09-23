[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCChargingStatusReq.md)

## SCC_ChargingStatusReq

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_ChargingStatusReq

**Valid for:**  CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_ChargingStatusReq ( byte SessionID[] )
```

### Description

The callback is called as soon as a Charging Status Request is received.

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.

### Return Values

—

### Example

—
