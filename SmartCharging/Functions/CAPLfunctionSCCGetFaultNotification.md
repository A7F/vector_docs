[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetFaultNotification.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » **SCC_GetFaultNotification**

# SCC_GetFaultNotification

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```
long SCC_GetFaultNotification ( char FaultCode[], char FaultMsg[] )
```

## Description

Gets the fault code and fault message (optional) of the V2G message header.

## Parameters

- **FaultCode**: Queries the fault code according to the specification (to the given char buffer).
- **FaultMsg**: Queries the fault message string.

## Return Values

- **0**: If no fault code is contained in the V2G header.
- **1**: If a fault code is contained in the V2G header. In this case, fault code and optionally fault message are copied to the output buffers. Missing fault message results in an empty string.

## Example

—
