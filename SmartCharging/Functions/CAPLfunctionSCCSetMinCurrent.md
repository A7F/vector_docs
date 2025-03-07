[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetMinCurrent.md)

# SCC_SetMinCurrent

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetMinCurrent

**Valid for:** CANoe DE • CANoe4SW DE

**Note:** This function needs a running SCC session in order to work. Make sure to call it only after the Session Setup Request message is sent.

## Function Syntax

```
long SCC_SetMinCurrent ( float MinCurrent )
```

## Description

Sets the minimum current for the message **ChargeParameterDiscoveryReq**. A default value can be set using the configuration file.

## Parameters

- **MinCurrent**: Minimum current value to be set.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—