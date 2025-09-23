[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetDurationResp.md)

## linGetDurationResp

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetDurationResp

### Valid for: CANoe DE

**Note:** [LIN bus statistics](../CAPLfunctionsLINOverview.md#BMBusStatistics) is deactivated by default and must be activated before calling this function. You can do this by calling function [linEnableStatistics](CAPLfunctionLINEnableStatistics.md) in an **on start {}** handler, see example below.

### Function Syntax

```plaintext
long linGetDurationResp(long channel, ValueSelector selector);
```

### Description

Gets the duration of the frame response of a LIN channel in microseconds. The kind of value to be returned (average, current, maximum or minimum) can be selected.

### Parameters

- **channel**: LIN channel (1…64).
- **selector**: Value selector:
  - eCurrValue = current
  - eMinValue = minimum
  - eMaxValue = maximum
  - eAvgValue = average

### Return Values

Duration of the frame response in microseconds, if LIN statistics is enabled; 0 otherwise.

### Example

```plaintext
on start
{
  linEnableStatistics(1, 1); // Enable LIN statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = linGetDurationResp(1, eCurrValue); // Current response duration on channel 1
  // … do something with the value, e.g.:
  write("Response duration: %i [us]", value);
}
```
