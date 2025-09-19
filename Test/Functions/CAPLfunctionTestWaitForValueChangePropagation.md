[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForValueChangePropagation.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » testWaitForValueChangePropagation

# testWaitForValueChangePropagation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long testWaitForValueChangePropagation();
```

## Description

Wait until value changes for system variables or value entities have been propagated through the simulation loop. This is especially important if the [asynchronous evaluation](../../../CANoeCANalyzer/Ribbon/File/Options/Measurement/MeasurementPerformanceAsyncBackgroundCheck.md) of constraints and conditions is activated.

## Parameters

—

## Return Values

- **-1**: General error, for example, functionality is not available.
- **0**: Wait successful

## Example

```plaintext
@vars::var1 = 3;
testWaitForValueChangePropagation();
// create checks, add constraints
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
