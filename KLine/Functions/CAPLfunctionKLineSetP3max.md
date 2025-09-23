[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetP3max.md)

[CAPL Functions](../../CAPLfunctions.md) » [K-Line](../CAPLfunctionsKLineOverview.md) » KLine_SetP3max

# KLine_SetP3max

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long KLine_SetP3max(dword P3max_us)
```

## Description

Sets the maximum time between the end of the server (ECU) response and start of a new client (tester) request. If no request is sent in this interval, the ECU can assume that the tester is no longer present.

## Parameters

- **P3max_us**: P3max in us  
  Value range: 0 – 10000000 (10 s).

## Return Values

- **0**: Success
- **< 0**: [Error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
on start
{
   KLine_SetP3Max(3000000); // P3max == 3 s
}
```
