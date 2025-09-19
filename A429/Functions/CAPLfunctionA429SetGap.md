# a429SetGap

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```
dword a429SetGap( a429word myA429word, dword gapValue );
```

## Description

This function sets the selector [gap](../CAPLfunctionsA429Selectors.md) of an ARINC word. The value is given in nanoseconds. You have to consider the bitrate on the corresponding channel. If the bitrate is high speed a value of 40000 (40 µs) specifies the standard gap of 4 bit times (as defined in [/1/](../../../CANoeCANalyzer/A429/A429References.md)). For low speed at 12500 kBit/s a value of 320000 (320 µs) is needed.

**Note:** This modifies the ARINC word attributes only. For transmission call the function [output](CAPLfunctionA429output.md).

## Parameters

- **myA429word**: ARINC word
- **gapValue**: gap in nanoseconds; value range [0; 1/8 bit time..1 second]; the value 0 forces the use of the [channel default value](../../../CANoeCANalyzer/A429/windows/hwConfig/hwConfigA429PageA429.md)

## Return Values

- **0**: gap not changed; value range exceeded
- **1**: gap value successfully changed

## Example

—

