[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSessionSetupReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_SessionSetupReq

# SCC_SessionSetupReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void SCC_SessionSetupReq ( byte SessionID[], byte EVCCID[] )
```

## Description

The callback is called as soon as a Session Setup Request is received.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF. If a new session is started, this ID is transferred.
- **EVCCID**: 6-byte long in ISO and 8-byte long in DIN.

## Return Values

—

## Example

—
