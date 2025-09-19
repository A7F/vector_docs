[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionCheckSignalMatch.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » CheckSignalMatch

# CheckSignalMatch

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long CheckSignalMatch(Signal aSignal, float aCompareValue); // form 1`
- `long CheckSignalMatch(dbEnvVar aEnvVar, float aCompareValue); // form 2`
- `long CheckSignalMatch(sysvar aSysVar, float aCompareValue); // form 3`
- `long CheckSignalMatch(sysvar aSysVar, int64 aCompareValue); // form 4`
- `long CheckSignalMatch(ServiceSignalNumber aSignal, float aCompareValue); // form 5`

## Description

Checks the given value against the value of signal, the system or the environment variable. The resolution of the signal is considered.

## Parameters

- **aSignal**: The signal to be polled.
- **aEnvVar**: The environment variable to be polled.
- **aSysVar**: The system variable to be polled. May also be a specific element of a variable of type struct or generic array.

  **Note**: Not available for a single element of a double or integer array.

- **aCompareValue**: Value which is compared to the signal or system variable value.

## Return Values

- **1**: If the condition is TRUE
- **0**: If the condition is violated or the signal or system variable is unavailable, i.e. was not on the bus yet
- **-1**: General error

## Example

**Example 1**

```c
// checks if the value of the signal or system variable matches a specified value
long result;
result = CheckSignalMatch(Node_SUT::Velocity, 80);
if (result != 1)
    TestStepFail("Value of signal matches not the value ‘80’!");
```

**Example 2**

```c
testfunction SignalCheck(signal * sig, float compareValue)
{
    // checks if the value of the signal matches a specified value
    long result;
    result = CheckSignalMatch(sig, compareValue);
    if (result != 1)
        TestStepFail("Value of signal matches not the value");
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
