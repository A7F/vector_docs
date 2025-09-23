[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINEnableStatistics.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linEnableStatistics

# linEnableStatistics

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `void linEnableStatistics(long channel, long flag); // Form 1`
- `void linEnableStatistics(long flag); // Form 2`

## Description

Enables or disables LIN statistics on a specific (Form 1) or all (Form 2) LIN channels.

**Note:** [LIN bus statistics](../CAPLfunctionsLINOverview.md#BMBusStatistics) for CAPL is disabled by default to avoid performance issues while measurement is running. However, you can enable it by calling these functions, e.g. in an **on start {}** handler (see example below).

## Parameters

- **channel**: LIN channel (1...64)
- **flag**: 0 = disable; 1 = enable

## Return Values

—

## Example

```plaintext
on start
{
  linEnableStatistics(1, 1); // Enable statistics on channel 1 or...
  //linEnableStatistics(1);    // on all channels
}

on key ‘d’
{
  linEnableStatistics(1, 0); // Disable statistics on channel 1
}
```
