[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCConnectionTimeoutInd.md)

# SCC_ConnectionTimeoutInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_ConnectionTimeoutInd

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```c
void SCC_ConnectionTimeoutInd ( byte SessionID[] )
```

## Description

The callback is called when a connection is closed due to inactivity.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
