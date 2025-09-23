[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetETFResolutionCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetETFResolutionCount

# linGetETFResolutionCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
[LIN bus statistics](../CAPLfunctionsLINOverview.md#BMBusStatistics) is deactivated by default and must be activated before calling this function. You can do this by calling function [linEnableStatistics](CAPLfunctionLINEnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```plaintext
long linGetETFResolutionCount(long channel);
```

## Description

Gets the total count of Event Triggered Frame (ETF) collision resolutions of a LIN channel.

## Parameters

- **channel**: LIN channel (1…64).

## Return Values

Total count of ETF collision resolutions, if LIN statistics is enabled; 0 otherwise.

## Example

```plaintext
on start
{
  linEnableStatistics(1, 1); // Enable LIN statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = linGetETFResolutionCount(1); // Resolution count on channel 1
  // … do something with the value …
}
```
