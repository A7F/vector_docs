# frGetFrameCount

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRGetFrameCount.md)

**CAPL Functions** » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frGetFrameCount

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
[FlexRay bus statistics](../CAPLfunctionsFlexrayOverview.md#BMBusStatistics) for CAPL is deactivated by default and must be activated before calling this function. You can do this by calling function [frEnableStatistics](CAPLfunctionFREnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```plaintext
long frGetFrameCount(long channel, long channelMask);
```

## Description

Gets the total count of frames on a FlexRay channel.

## Parameters

- **channel**: FlexRay channel (1…32).
- **channelMask**: Channel mask
  - 1 = subchannel A
  - 2 = subchannel B

## Return Values

Total count of frames, if FlexRay statistics is enabled; 0 otherwise.

## Example

```plaintext
on start
{
  frEnableStatistics(1, 1); // Enable FlexRay statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = frGetFrameCount(1, 1); // Channel 1, subchannel A
  // … do something with the value …
}
```
