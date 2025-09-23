[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetW4Tester.md)

[CAPL Functions](../../CAPLfunctions.md) » [K-Line](../CAPLfunctionsKLineOverview.md) » KLine_SetW4Tester

# KLine_SetW4Tester

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long KLine_SetW4Tester( dword  W4_us)
```

## Description

Sets the W4 timing of the tester between keybyte2 and keybyte2Not.

## Parameters

- **W4_us**: W4 time in us.  
  Value range: 0 - 650000

## Return Values

On success 0, otherwise a value less than 0.

## Example

—

[KLine_SetW5Tester](CAPLfunctionKLineSetW5Tester.md)
