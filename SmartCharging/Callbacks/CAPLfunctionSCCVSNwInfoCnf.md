[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCVSNwInfoCnf.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_VS_Nw_Info_Cnf

# SCC_VS_Nw_Info_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```c
void SCC_VS_Nw_Info_Cnf ( byte SourceMacAddress[], long NumAvLn, byte NID[] )
```

## Description

The callback is called as soon as a **VS_Nw_Info.Cnf** message is received. This is a response of the QCA7000 chip when using link status polling. (Additional data cannot be queried at the moment.)

## Parameters

- **SourceMacAddress**: MAC address of sender.
- **NumAvLn**: Number of AVLANs (> 0 denotes an established link).
- **NID**: Network ID (7 byte).

## Return Values

—

## Example

—
