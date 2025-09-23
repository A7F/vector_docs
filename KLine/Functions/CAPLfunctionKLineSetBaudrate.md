[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetBaudrate.md)

**CAPL Functions** » **K-Line** » **KLine_SetBaudrate**

# KLine_SetBaudrate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long KLine_SetBaudrate(dword baudrate)
```

## Description

Allows changing the baudrate during the measurement.

## Parameters

- **baudrate**: Value range: 200 baud - 115200 baud.

## Return Values

On success 0, otherwise a value less than 0.

## Example

—

[KLine_SetUARTParameter](CAPLfunctionKLineSetUARTParameter.md)
