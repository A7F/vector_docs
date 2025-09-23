[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetW5Tester.md)

**CAPL Functions** » [K-Line](../CAPLfunctionsKLineOverview.md) » KLine_SetW5Tester

# KLine_SetW5Tester

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long KLine_SetW5Tester( dword  W5_us)
```

## Description

Sets the W5 timing before the tester starts to transmit the address byte.

## Parameters

- **W5_us**: W5 time in us.  
  Value range: 0 – 10,000,000

## Return Values

On success 0, otherwise a value less than 0.

## Example

—

[KLine_SetW4Tester](CAPLfunctionKLineSetW4Tester.md)
