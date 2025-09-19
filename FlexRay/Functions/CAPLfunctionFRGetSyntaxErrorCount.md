[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRGetSyntaxErrorCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frGetSyntaxErrorCount

# frGetSyntaxErrorCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
[FlexRay bus statistics](../CAPLfunctionsFlexrayOverview.md#BMBusStatistics) for CAPL is deactivated by default and must be activated before calling this function. You can do this by calling function [frEnableStatistics](CAPLfunctionFREnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```plaintext
long frGetSyntaxErrorCount(long channel, long channelMask);
```

## Description

Gets the total count of syntax errors of a FlexRay channel.

## Parameters

- **channel**  
  FlexRay channel (1…32).

- **channelMask**  
  Channel mask
  - 1 = subchannel A
  - 2 = subchannel B

## Return Values

Total count of syntax errors, if FlexRay statistics is enabled; 0 otherwise.

## Example

```plaintext
on start
{
  frEnableStatistics(1, 1); // Enable FlexRay statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = frGetSyntaxErrorCount(1, 2); // Channel 1, subchannel B
  // … do something with the value …
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
