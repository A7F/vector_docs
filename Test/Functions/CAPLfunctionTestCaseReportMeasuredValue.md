[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCaseReportMeasuredValue.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestCaseReportMeasuredValue

# TestCaseReportMeasuredValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void TestCaseReportMeasuredValue(char semanticName[], float value);`
- `void TestCaseReportMeasuredValue(char semanticName[], float value, char unit[]);`
- `void TestCaseReportMeasuredValue(char semanticName[], long value);`
- `void TestCaseReportMeasuredValue(char semanticName[], long value, char unit[]);`
- `void TestCaseReportMeasuredValue(char semanticName[], char text[]);`
- `void TestCaseReportMeasuredValue(char semanticName[], char text, char unit[]);`
- `void TestCaseReportMeasuredValue(char semanticName[], signal sig);`
- `void TestCaseReportMeasuredValue(char semanticName[], signal sig, char unit[]);`
- `void TestCaseReportMeasuredValue(char semanticName[], sysvar aSysVar);`
- `void TestCaseReportMeasuredValue(char semanticName[], sysvar aSysVar, char unit[]);`
- `void TestCaseReportMeasuredValue(char semanticName[], dbEnvVar aEnvVar);`
- `void TestCaseReportMeasuredValue(char semanticName[], dbEnvVar aEnvVar, char unit[]);`

## Description

Adds a report entry in the measured values table for the given parameter at the test case level. Accepted parameters are: user defined values, signals, system variables and environment variables.

**Note**: If the function is called several times inside a test case using the same semantic name, only the last value will be reported in the measured values table.

## Parameters

- **semanticName**: Semantic name for one reported value.
- **value**: Numerical value to be displayed in the measured values table.
- **text**: String value to be displayed in the measured values table.
- **sig**: Value of a signal to be reported in the measured values table.
- **aSysVar**: Value of a system variable to be reported in the measured values table. Currently supported types for system variables are: integer, float and string.
- **aEnvVar**: Value of an environment variable to be reported in the measured values table. Currently supported types for environment variables are: integer, float and string.
- **unit**: Optional. User defined unit text to be displayed in the measured value. If omitted the default unit will be displayed.

## Return Values

—

## Example

```plaintext
testcase TestMeasuredValues()
{
  double acc;
  TestCaseTitle("", "Report Measured Values");

  TestCaseReportMeasuredValue("Version", "1.0");
  TestCaseReportMeasuredValue("Start time", 210, "ms");

  TestCaseReportMeasuredValue("Crash", VehicleMotion::CrashDetected);
  TestCaseReportMeasuredValue("Acceleration", sysvar::SystemUnderTest::Accelerate);

  TestStep("", "Value Conversion");
  acc = @sysvar::SystemUnderTest::Accelerate * 1000.0 / 3600.0;
  TestCaseReportMeasuredValue("Acceleration", acc, "mp/s2");

  TestWaitForTimeout(2000);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)