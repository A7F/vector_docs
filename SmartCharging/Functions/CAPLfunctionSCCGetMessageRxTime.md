# SCC_GetMessageRxTime

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetMessageRxTime.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » SCC_GetMessageRxTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Note

- This function can be called only within the assigned callback. It is used to query the details of a SLAC or V2G message.
- The result of this query is the message timestamp as seen in the Trace window. It is a value taken from your CANoe DE product, in contrast to [SCC_GetTimestamp](CAPLfunctionSCCGetTimestamp.md), which returns a timestamp parameter that is sent inside a V2G message.

## Function Syntax

- `qword SCC_GetMessageRxTime()` // form 1
- `void SCC_GetMessageRxTime(dword& TimeNsHigh, dword& TimeNsLow)` // form 2

## Description

Gets the CANoe DE product internal timestamp of the message receipt event, i.e., the simulation time of your CANoe DE product, via references. The function is available for all kinds of message callbacks.

## Parameters

**Form 2**

- **TimeNsHigh**: Gets the high 32 bit of the timestamp in ns (via reference).
- **TimeNsLow**: Gets the low 32 bit of the timestamp in ns (via reference).

## Return Values

Form 1: Time stamp in nanoseconds.

## Example

—
