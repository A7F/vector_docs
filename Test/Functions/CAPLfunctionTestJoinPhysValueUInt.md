[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinPhysValueUInt.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinPhysValueUInt

# TestJoinPhysValueUInt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestJoinPhysValueUInt(valueHandle * value, qword awaitedValue); // form 1`
- `long TestJoinPhysValueUInt(valueHandle * value, qword awaitedValue, dword waitForValueUpdate); // form 2`

## Description

Completes the current set of **joined events** with the transmitted event. This function can only be used for **valueHandles** with an unsigned integer data type. This function does not wait.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **awaitedValue**: Value which is awaited.
- **waitForSignalUpdate**: Condition should be checked immediately when the set of joined events is evaluated by [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md), or condition should be checked when the next message with the given signal will arrive.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```plaintext
long ret;
dword index = 0;
ret = testJoinPhysValueUInt(ErrorSignal[LeftMirror], 1, 1);

index = TestWaitForAnyJoinedEvent(2000);
```

[TestJoinPhysValueFloat](CAPLfunctionTestJoinPhysValueFloat.md) • [TestJoinPhysValueSInt](CAPLfunctionTestJoinPhysValueSInt.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
