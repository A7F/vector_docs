[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetDetectedRespErrorCount.md)

**CAPL Functions** » **LIN** » linGetDetectedRespErrorCount

# linGetDetectedRespErrorCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
[LIN bus statistics](../CAPLfunctionsLINOverview.md#BMBusStatistics) is deactivated by default and must be activated before calling this function. You can do this by calling function [linEnableStatistics](CAPLfunctionLINEnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```plaintext
long linGetDetectedRespErrorCount(long channel);
```

## Description

Gets the total count of response errors detected by a response error bit on a LIN channel.

## Parameters

- **channel**: LIN channel (1…64).

## Return Values

Total count of response errors detected by response error bit, if LIN statistics is enabled; 0 otherwise.

## Example

```plaintext
on start
{
  linEnableStatistics(1, 1); // Enable LIN statistics on channel 1
}

void myStatisticFunc()
{
  long count;

  count = linGetDetectedRespErrorCount(1); // Detected response errors on channel 1
  // … do something with the count …
}
```
