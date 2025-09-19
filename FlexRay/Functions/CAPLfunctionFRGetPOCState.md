[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRGetPOCState.md)

**CAPL Functions** » **FlexRay** » **frGetPOCState**

# frGetPOCState

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

**Note**

[FlexRay bus statistics](../CAPLfunctionsFlexrayOverview.md#BMBusStatistics) for CAPL is deactivated by default and must be activated before calling this function. You can do this by calling function [frEnableStatistics](CAPLfunctionFREnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```plaintext
int frGetPOCState(long channel, long channelMask);
```

## Description

Gets the current POC state of a FlexRay channel. For a list of POC states, see description of event procedure **on frPOCState**.

## Parameters

- **channel**: FlexRay channel (1…32).
- **channelMask**: Channel mask
  - 1 = subchannel A
  - 2 = subchannel B

## Return Values

The current POC state, if FlexRay statistics is enabled; 0 otherwise.

## Example

```plaintext
on start
{
  frEnableStatistics(1, 1); // Enable FlexRay statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = frGetPOCState(1, 2); // Channel 1, subchannel B
  // … do something with the value …
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
