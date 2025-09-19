[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinSignalMatch.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinSignalMatch

# TestJoinSignalMatch

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestJoinSignalMatch (Signal aSignal, float CompareValue); // form 1`
- `long TestJoinSignalMatch (dbEnvVar aEnvVar, float CompareValue); // form 2`
- `long TestJoinSignalMatch (sysvar aSysVar, float CompareValue); // form 3`
- `long TestJoinSignalMatch (Signal aSignal, float CompareValue, word waitForSignalUpdate); // form 4`
- `long TestJoinSignalMatch (sysvar aSysVar, int64 CompareValue); // form 5`
- `long TestJoinSignalMatch (ServiceSignalNumber aSignal, float CompareValue); // form 6`
- `long TestJoinSignalMatch (ServiceSignalNumber aSignal, float CompareValue, word waitForSignalUpdate); // form 7`

## Description

Completes the current set of "joined events or system variables" with the transmitted event. This function does not wait.

By default, this condition will be checked immediately when the set of joined events is evaluated by [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) and may not wait for a value change. It is also possible to delay the checking of the condition until the next message with the given signal arrives.

## Parameters

- **aSignal**: Signal that should be awaited with a value to which the given value matches.
- **aEnvVar**: Environment variable that should be awaited with a value to which the given value matches.
- **aSysVar**: System variable that should be awaited with a value to which the given value matches. May also be a specific element of a variable of type struct or generic array.

  **Note**: Not available for a single element of a double or integer array.

- **aCompareValue**: Value which is compared to the signal value.
- **waitForSignalUpdate**: Condition should be checked immediately when the set of joined events is evaluated by [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md), or condition should be checked when the next message with the given signal will arrive.

## Return Values

- **-3**: Join error
- **-2**: Signal or system variable is not valid
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```c
// waits until signal or system variable ‘Velocity’ matches to a specific value
long result;
dword index = 0;
result = TestJoinSignalMatch(Node_SUT::Velocity, 80);
// ... other join events
TestJoinEnvVarEvent(MyEnvVar);
TestJoinTextEvent("ErrorFrame occurred!");

index = TestWaitForAllJoinedEvents(500);
```

[TestWaitForSignalMatch](CAPLfunctionTestWaitForSignalMatch.md) • [TestJoinRawSignalMatch](CAPLfunctionTestJoinRawSignalMatch.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
