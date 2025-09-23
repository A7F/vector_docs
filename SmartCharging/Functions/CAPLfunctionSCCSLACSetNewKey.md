[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACSetNewKey.md)

# SCC_SLAC_SetNewKey

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Simulation](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_SetNewKey

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SCC_SLAC_SetNewKey(byte NMK[], byte NID[])
```

## Description

This function stores the NMK and NID as user defined Key.

## Parameters

- **NMK**: Network Membership Key (16 byte)
- **NID**: Network ID (7 byte hexadecimal number)

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

```c
StoreOwnKey()
{
  byte NMK[16];
  byte NID[7];

  // Generate random NMK and according NID
  SCC_GenerateRandomData(NMK, elcount(NMK));
  SCC_SLAC_GenerateNID(NMK, NID);

  // Store as user defined Key
  SCC_SLAC_SetNewKey(NMK, NID);
}
```
