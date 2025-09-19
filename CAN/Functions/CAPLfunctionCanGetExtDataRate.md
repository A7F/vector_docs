# canGetExtDataRate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long canGetExtDataRate(long channel, ValueSelector selector);
```

## Description

Gets the rate of extended data frames of a CAN channel in frames per second [fr/s]. The kind of value to be returned (average, current, maximum or minimum) can be selected.

## Parameters

- **channel**: CAN channel (1…32).
- **selector**: Value selector:
  - eCurrValue = current
  - eMinValue = minimum
  - eMaxValue = maximum
  - eAvgValue = average

## Return Values

Rate of extended data frames in frames per second, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Extended data frame rate on CAN1: %i [fr/s]", canGetExtDataRate(1, eCurrValue));
```
