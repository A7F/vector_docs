# canEnableStatistics

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

- `void canEnableStatistics(long channel, long flag); // Form 1`
- `void canEnableStatistics(long flag); // Form 2`

## Description

Enables or disables CAN statistics on a specific (Form 1) or all (Form 2) CAN channels.

CAN statistics for CAPL is enabled by default, but you can disable it to prevent performance issues when running a measurement. You can do this for example in an **on start** handler, see below.

## Parameters

- **channel**: CAN channel (1…32).
- **flag**:
  - 0 = disable
  - 1 = enable

## Return Values

—

## Example

```plaintext
on start
{
  canEnableStatistics(0); // Disable CAN statistics on all channels
}

on key ‘e’
{
  canEnableStatistics(1, 1); // Enable CAN statistics on channel 1
}
```
