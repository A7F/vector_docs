# canGetOverloadFrameRate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetOverloadFrameRate(long channel, ValueSelector selector);
```

## Description

Gets the rate of overload frames of a CAN channel in frames per second [fr/s]. The kind of value to be returned (average, current, maximum or minimum) can be selected.

## Parameters

- **channel**: CAN channel (1…32).
- **selector**: Value selector:
  - eCurrValue = current
  - eMinValue = minimum
  - eMaxValue = maximum
  - eAvgValue = average

## Return Values

Rate of overload frames in frames per second, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Average overload frame rate of CAN1: %i [fr/s]", canGetOverloadFrameRate(1, eAvgValue));
```
