[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinImplValueInRangeSInt.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinImplValueInRangeSInt

# TestJoinImplValueInRangeSInt

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestJoinImplValueInRangeSInt(valueHandle * value, int64 aLowLimit, int64 aHighLimit); // form 1`
- `long TestJoinImplValueInRangeSInt(valueHandle * value, int64 aLowLimit, int64 aHighLimit, word waitForSignalUpdate); // form 2`

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

By default, this condition will be checked immediately when the set of joined events is evaluated by [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) and may not wait for a value change. It is also possible to delay the checking of the condition until the next message with the given signal arrives.

This function can only be used for **valueHandles** with a signed integer data type. It cannot be used for system variables or bus system signals.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **aLowLimit**: Lower limit of the value.
- **aHighLimit**: Higher limit of the value.
- **waitForSignalUpdate**: Condition should be checked immediately when the set of joined events is evaluated by [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md), or condition should be checked when the next message with the given signal will arrive.

## Return Values

- **-3**: Join error
- **-2**: Type of the value is not valid
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```plaintext
long ret;
dword index = 0;
ret = testJoinImplValueInRangeSInt(MirrorStatus[CANoe].Temperature, 20, 30);

// ... other join events

index = TestWaitForAnyJoinedEvent(2000);
```

[TestJoinImplValueInRangeFloat](CAPLfunctionTestJoinImplValueInRangeFloat.md) • [TestJoinImplValueInRangeUInt](CAPLfunctionTestJoinImplValueInRangeUInt.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
