# frGetBoundaryViolationCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

[FlexRay bus statistics](../CAPLfunctionsFlexrayOverview.md#BMBusStatistics) for CAPL is deactivated by default and must be activated before calling this function. You can do this by calling function [frEnableStatistics](CAPLfunctionFREnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```
long frGetBoundaryViolationCount(long channel, long channelMask);
```

## Description

Gets the total count of boundary violations of a FlexRay channel.

## Parameters

- **channel**  
  FlexRay channel (1…32).

- **channelMask**  
  Channel mask
  - 1 = subchannel A
  - 2 = subchannel B

## Return Values

Total count of boundary violations, if FlexRay statistics is enabled; 0 otherwise.

## Example

```c
on start
{
  frEnableStatistics(1, 1); // Enable FlexRay statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = frGetBoundaryViolationCount(1, 2); // Channel 1, subchannel B
  // … do something with the value …
}
```
