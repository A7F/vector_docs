[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanEnableStatistics.md)

**CAPL Functions** » [CAN](../CAPLfunctionsCANOverview.md) » canEnableStatistics

# canEnableStatistics

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

- `void canEnableStatistics(long channel, long flag); // Form 1`
- `void canEnableStatistics(long flag); // Form 2`

## Description

Enables or disables CAN statistics on a specific (Form 1) or all (Form 2) CAN channels.

CAN statistics for CAPL is enabled by default, but you can disable it to prevent performance issues when running a measurement. You can do this for example in an **on start** handler, see below.

## Parameters

- **channel**: CAN channel (1…32).
- **flag**:
  - 0 = disable
  - 1 = enable

## Return Values

—

## Example

```plaintext
on start
{
  canEnableStatistics(0); // Disable CAN statistics on all channels
}

on key ‘e’
{
  canEnableStatistics(1, 1); // Enable CAN statistics on channel 1
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)