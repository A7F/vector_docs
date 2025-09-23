[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMAmpMapCnf.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_CM_Amp_Map_Cnf

# SCC_CM_Amp_Map_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CM_Amp_Map_Cnf(byte RunID[], byte SourceMac[], dword ResType)
```

## Description

The callback is called as soon as a `CM_Amp_Map.Cnf` message is received.

## Parameters

- **RunID**: 8-byte long run ID
- **SourceMac**: MAC address of sender
- **ResType**:
  - 0x00 = Success
  - 0x01 = Failure

## Return Values

—

## Example

—
