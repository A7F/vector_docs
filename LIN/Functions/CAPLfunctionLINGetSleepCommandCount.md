[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetSleepCommandCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetSleepCommandCount

# linGetSleepCommandCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
[LIN bus statistics](../CAPLfunctionsLINOverview.md#BMBusStatistics) is deactivated by default and must be activated before calling this function. You can do this by calling function [linEnableStatistics](CAPLfunctionLINEnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```plaintext
long linGetSleepCommandCount(long channel);
```

## Description

Gets the total count of go-to-sleep requests of a LIN channel.

## Parameters

- **channel**: LIN channel (1…64).

## Return Values

Total count of go-to-sleep requests, if LIN statistics is enabled; 0 otherwise.

## Example

```plaintext
on start
{
  linEnableStatistics(1, 1); // Enable LIN statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = linGetSleepCommandCount(1); // Sleep command count on channel 1
  // … do something with the value, e.g.:
  if (value > 100)
  {
    write("More than 100 go-to-sleep requests on channel 1 detected!");
  }
}
```
