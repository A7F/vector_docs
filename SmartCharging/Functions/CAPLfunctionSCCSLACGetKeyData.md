[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetKeyData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Simulation](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_GetKeyData

# SCC_SLAC_GetKeyData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
void SCC_SLAC_GetKeyData ( byte NID[], byte NMK[] )
```

## Description

Gets the currently stored NID and NMK values (when automatic SLAC is used).

## Parameters

- **NID**: Queries the Network ID (7 byte hexadecimal number) (to the given byte buffer).
- **NMK**: Queries the Network Membership Key (16 byte) (to the given byte buffer).

## Return Values

—

## Example

—
