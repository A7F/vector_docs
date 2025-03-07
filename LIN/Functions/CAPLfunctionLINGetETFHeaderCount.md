[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetETFHeaderCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetETFHeaderCount

# linGetETFHeaderCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
[LIN bus statistics](../CAPLfunctionsLINOverview.md#BMBusStatistics) is deactivated by default and must be activated before calling this function. You can do this by calling function [linEnableStatistics](CAPLfunctionLINEnableStatistics.md) in an **on start {}** handler, see example below.

## Function Syntax

```plaintext
long linGetETFHeaderCount(long channel);
```

## Description

Gets the total count of Event Triggered Frame (ETF) headers of a LIN channel.

## Parameters

- **channel**: LIN channel (1…64).

## Return Values

Total count of ETF headers, if LIN statistics is enabled; 0 otherwise.

## Example

```plaintext
on start
{
  linEnableStatistics(1, 1); // Enable LIN statistics on channel 1
}

void myStatisticFunc()
{
  long value;

  value = linGetETFHeaderCount(1); // Header count on channel 1
  // … do something with the value …
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)