# a429CalcBitLength

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword a429CalcBitLength( long channel, dword BitTimes );
```

## Description

For every channel there is a relation between a bit time and the length of a bit time. This relation is determined by the channel bitrate. In order to make it easier to provide the gap length [a429SetGap](CAPLfunctionA429SetGap.md) in bit times this function converts these values for a given channel.

## Parameters

- **channel**: valid Tx channel
- **BitTimes**: 1..1048576 (0x1..0x10000; 0.125..131072 bit times; in steps of 1/8 bit)

## Return Values

- **0**: invalid channel selected
- **1**: parameter BitTimes exceeded valid range
- **2**: result is outside of valid range for the given channel parameters
- **1000..0xFFFFFFFF**: time in nanoseconds

## Example

—
