# canGetBurstTime

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long canGetBurstTime(long channel, ValueSelector selector);
```

## Description

Gets the burst time of a CAN channel in microseconds. The kind of value to be returned (average, current, maximum or minimum) can be selected.

## Parameters

- **channel**: CAN channel (1…32).
- **selector**: Value selector:
  - eCurrValue = current
  - eMinValue = minimum
  - eMaxValue = maximum
  - eAvgValue = average

## Return Values

Burst time in microseconds, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Current burst time CAN1: %i", canGetBurstTime(1, eCurrValue));
```
