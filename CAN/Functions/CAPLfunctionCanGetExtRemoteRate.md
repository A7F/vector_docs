### Function Syntax

```plaintext
long canGetExtRemoteRate(long channel, ValueSelector selector);
```

### Description

Gets the rate of extended remote frames of a CAN channel in frames per second [fr/s]. The kind of value to be returned (average, current, maximum or minimum) can be selected.

### Parameters

- **channel**: CAN channel (1…32).
- **selector**: Value selector:
  - `eCurrValue = current`
  - `eMinValue = minimum`
  - `eMaxValue = maximum`
  - `eAvgValue = average`

### Return Values

Rate of extended remote frames in frames per second, if CAN statistics is enabled; 0 otherwise.

### Example

```plaintext
write("Extended remote frame rate on CAN1: %i [fr/s]", canGetExtRemoteRate(1, eCurrValue));
```

[Valid for: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE](../../../Shared/FeatureAvailability.md)
