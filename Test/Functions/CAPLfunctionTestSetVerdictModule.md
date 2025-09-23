# TestSetVerdictModule

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void TestSetVerdictModule (Verdict aVerdict);
```

## Description

This function sets the verdict of the test module. With this function the automatic verdict propagation of test cases to the test module can be influenced later.

E.g. this function can be used within the test controlling to conduct a test case "on probe" and to reset the verdict to "pass" in case "fail".

## Parameters

- **aVerdict**:
  - `0`: pass
  - `1`: fail
  - `2`: none
  - `3`: inconclusive
  - `4`: error in test system

## Return Values

—

## Example

See example: [TestSetVerdictModule](CAPLfunctionsTFSExampleTestSetVerdictModule.md)

[TestGetVerdictModule](CAPLfunctionTestGetVerdictModule.md) • [TestGetVerdictLastTestCase](CAPLfunctionTestGetVerdictLastTestCase.md) • [Test Results - Verdicts](../../../CANoeCANalyzer/Test/TestVerdicts.md)
