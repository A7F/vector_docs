# canGetErrorFrameRate

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetErrorFrameRate(long channel, ValueSelector selector);
```

## Description

Gets the error frame rate of a CAN channel in frames per second [fr/s]. The kind of value to be returned (average, current, maximum or minimum) can be selected.

## Parameters

- **channel**: CAN channel (1…32).
- **selector**: Value selector:
  - `eCurrValue` = current
  - `eMinValue` = minimum
  - `eMaxValue` = maximum
  - `eAvgValue` = average

## Return Values

Error frame rate in frames per second, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Error frame rate on CAN1: %i [fr/s]", canGetErrorFrameRate(1, eCurrValue));
```
