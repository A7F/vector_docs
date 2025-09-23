# SCC_GetHeaderData

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetHeaderData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » SCC_GetHeaderData

## Valid for:  
CANoe DE • CANoe4SW DE

---

### Note

This function can be called only within the assigned callback. It is used to query the details of a SLAC or V2G message.

---

## Function Syntax

```plaintext
void SCC_GetHeaderData ( byte HeaderData[] )
```

## Description

Gets the SDP or V2G message header (to the output buffer).

## Parameters

- **HeaderData**: Queries the 8 byte header data (to the given byte buffer).

## Return Values

—

## Example

—

---
