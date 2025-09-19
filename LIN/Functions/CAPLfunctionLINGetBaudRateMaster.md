[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetBaudRateMaster.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linGetBaudRateMaster

# linGetBaudRateMaster

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
[LIN bus statistics](../CAPLfunctionsLINOverview.md#BMBusStatistics) is deactivated by default and must be activated before calling this function. You can do this by calling function [linEnableStatistics](CAPLfunctionLINEnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```plaintext
long linGetBaudRateMaster(long channel, ValueSelector selector);
```

## Description

Gets the measured baudrate of the master node on a LIN channel in bits per second [bit/s]. The kind of value to be returned (average, current, maximum or minimum) can be selected.

## Parameters

- **channel**: LIN channel (1…64).
- **selector**: Value selector:
  - eCurrValue = current
  - eMinValue = minimum
  - eMaxValue = maximum
  - eAvgValue = average

## Return Values

Baudrate of the master node in bits per second, if LIN statistics is enabled; 0 otherwise.

## Example

```plaintext
on start
{
  linEnableStatistics(1, 1); // Enable LIN statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = linGetBaudRateMaster(1, eCurrValue); // Current frame cycle time on channel 1
  // … do something with the value …
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
