[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestIsAsynchronousCheckEvaluationEnabled.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » testIsAsynchronousCheckEvaluationEnabled

# testIsAsynchronousCheckEvaluationEnabled

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long testIsAsynchronousCheckEvaluationEnabled();
```

## Description

This function is used to check if background checks are evaluated asynchronously.

## Parameters

—

## Return Values

- **0**: Asynchronous evaluation is not enabled.
- **1**: Asynchronous evaluation is enabled.

## Example

```plaintext
result = testIsAsynchronousCheckEvaluationEnabled ();
if (result == 1)
  TestStep("", "Asynchronous evaluation of background checks enabled");
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)