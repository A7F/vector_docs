[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFREnableStatistics.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frEnableStatistics

# frEnableStatistics

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void frEnableStatistics(long channel, long flag); // Form 1`
- `void frEnableStatistics(long flag); // Form 2`

## Description

Enables or disables FlexRay statistics on a specific (Form 1) or all (Form 2) FlexRay channels.

**Note**: [FlexRay bus statistics](../CAPLfunctionsFlexrayOverview.md#BMBusStatistics) for CAPL is disabled by default to avoid performance issues while measurement is running. However, you can enable it by calling these functions, e.g. in an **on start {}** handler (see example below).

## Parameters

- **channel**: FlexRay channel (1…32).
- **flag**: 0 = disable; 1 = enable

## Return Values

—

## Example

```plaintext
on start {
  frEnableStatistics(1, 1); // Enable statistics on channel 1 or...
  //frEnableStatistics(1);    // on all channels
}

on key ‘d’ {
  frEnableStatistics(1, 0); // Disable statistics on channel 1
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)