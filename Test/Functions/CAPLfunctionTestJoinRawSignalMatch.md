[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinRawSignalMatch.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinRawSignalMatch

# TestJoinRawSignalMatch

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `TestJoinRawSignalMatch(dbSignal aSignal, int64 value);` // form 1
- `TestJoinRawSignalMatch(char aSignalName[], int64 value);` // form 2
- `TestJoinRawSignalMatch(dbSignal aSignal, byte data[], dword dataLength);` // form 3
- `TestJoinRawSignalMatch(char aSignalName[], byte data[], dword dataLength);` // form 4

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

By default, this condition will be checked immediately when the set of joined events is evaluated by [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) and may not wait for a value change. It is also possible to delay the checking of the condition until the next message with the given signal arrives.

## Parameters

- **aSignal**: The signal.
- **aSignalName**: Name of the signal.
- **value**: Signal value to be set.
- **data**: The data bytes of the signal.
- **dataLength**: Length of the data.

**Note**: The **int64** parameter is interpreted as **qword** and will be casted according to the signal type. If a byte comparison is required, a byte array should be used.

## Return Values

- **-3**: Join error
- **-2**: Signal is not valid
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```plaintext
// waits until signal ‘Velocity’ matches to a specific value
long result;
dword index = 0;
result = TestJoinRawSignalMatch(Node_SUT::Velocity, 0.8);
// ... other join events
TestJoinEnvVarEvent(MyEnvVar);
TestJoinTextEvent("ErrorFrame occurred!");

index = TestWaitForAllJoinedEvents(500);
```

[TestJoinSignalMatch](CAPLfunctionTestJoinSignalMatch.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)