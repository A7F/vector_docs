# frGetBoundaryViolationRate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
[FlexRay bus statistics](../CAPLfunctionsFlexrayOverview.md#BMBusStatistics) for CAPL is deactivated by default and must be activated before calling this function. You can do this by calling function [frEnableStatistics](CAPLfunctionFREnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```plaintext
long frGetBoundaryViolationRate(long channel, ValueSelector selector, long channelMask);
```

## Description

Gets the rate of boundary violations of a FlexRay channel in frames per second [fr/s]. The kind of value to be returned (average, current, maximum or minimum) can be selected.

## Parameters

- **channel**  
  FlexRay channel (1…32).

- **selector**  
  Value selector:
  - eCurrValue = current
  - eMinValue = minimum
  - eMaxValue = maximum
  - eAvgValue = average

- **channelMask**  
  Channel mask
  - 1 = subchannel A
  - 2 = subchannel B

## Return Values

Rate of boundary violations in frames per second, if FlexRay statistics is enabled; 0 otherwise.

## Example

```plaintext
on start
{
  frEnableStatistics(1, 1); // Enable FlexRay statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = frGetBoundaryViolationRate(1, eMaxValue, 1); // Channel 1, maximum, subchannel A
  // … do something with the value …
}
```
