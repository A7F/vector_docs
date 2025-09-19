# frGetBusLoadDynamic

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**

[FlexRay bus statistics](../CAPLfunctionsFlexrayOverview.md#BMBusStatistics) for CAPL is deactivated by default and must be activated before calling this function. You can do this by calling function [frEnableStatistics](CAPLfunctionFREnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```plaintext
double frGetBusLoadDynamic(long channel, ValueSelector selector, long channelMask);
```

## Description

Gets the busload of the dynamic segment for data frames of a FlexRay channel in percent. The kind of value to be returned (average, current, maximum or minimum) can be selected.

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

Dynamic busload in percent, if FlexRay statistics is enabled; 0 otherwise.

## Example

```plaintext
on start
{
  frEnableStatistics(1, 1); // Enable FlexRay statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = frGetBusLoadDynamic(1, eAvgValue, 1); // Channel 1, average, subchannel A
  // … do something with the value …
}
```
