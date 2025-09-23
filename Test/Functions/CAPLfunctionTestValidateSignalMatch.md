# TestValidateSignalMatch

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestValidateSignalMatch (char aTestStep[], Signal aSignal, float aCompareValue); // form 1`
- `long TestValidateSignalMatch (char aTestStep[], dbEnvVar aEnvVar, float aCompareValue); // form 2`
- `long TestValidateSignalMatch (char aTestStep[], sysvar aSysVar, float aCompareValue); // form 3`
- `long TestValidateSignalMatch (char aTestStep[], sysvar aSysVar, int64 aCompareValue); // form 4`
- `long TestValidateSignalMatch (char aTestStep[], ServiceSignalNumber aSignal, float aCompareValue); // form 5`

## Description

Checks the given value against the value of the signal, the system variable or the environment variable. The resolution of the signal is considered. The test step is evaluated as either passed or failed depending on the results.

## Parameters

- **aTestStep**: Name of the test step for the test report.
- **aSignal**: The signal to be polled.
- **aEnvVar**: The environment variable to be polled.
- **aSysVar**: System Variable to be polled. May also be a specific element of a variable of type struct or generic array.
  - **Note**: Not available for a single element of a double or integer array.
- **aCompareValue**: Value which is compared to the signal value.

## Return Values

- **0**: Correct functionality
- **-1**: General error

## Example

```c
// validates the value of the signal against the given value
long result;
result = TestValidateSignalMatch("Check Velocity", Node_SUT::Velocity, 80);
```
