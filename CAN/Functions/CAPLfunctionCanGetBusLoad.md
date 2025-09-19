# canGetBusLoad

**Valid for**: CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long canGetBusLoad(long channel, ValueSelector selector);
```

## Description

Gets the busload of a CAN channel in percent. The kind of value to be returned (average, current, maximum or minimum) can be selected.

## Parameters

- **channel**: CAN channel (1…32).
- **selector**: Value selector:
  - eCurrValue = current
  - eMinValue = minimum
  - eMaxValue = maximum
  - eAvgValue = average

## Return Values

Busload in percent, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
long value;

value = canGetBusLoad(1, eAvgValue); // Channel 1, average
// Do something with the value, e.g.:
write("Average busload CAN1: %ld", value);
```
