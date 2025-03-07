[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinSignalOutsideRange.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinSignalOutsideRange

# TestJoinSignalOutsideRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestJoinSignalOutsideRange (Signal aSignal, float aLowLimit, float aHighLimit); // form 1`
- `long TestJoinSignalOutsideRange (dbEnvVar aEnvVar, float aLowLimit, float aHighLimit); // form 2`
- `long TestJoinSignalOutsideRange (sysvar aSysVar, float aLowLimit, float aHighLimit); // form 3`
- `long TestJoinSignalOutsideRange (Signal aSignal, float aLowLimit, float aHighLimit, word waitForSignalUpdate); // form 4`
- `long TestJoinSignalOutsideRange (sysvar aSysVar, int64 aLowLimit, int64 aHighLimit); // form 5`
- `long TestJoinSignalOutsideRange (ServiceSignalNumber aSignal, float aLowLimit, float aHighLimit); // form 6`
- `long TestJoinSignalOutsideRange (ServiceSignalNumber aSignal, float aLowLimit, float aHighLimit, word waitForSignalUpdate); // form 7`

## Description

Completes the current set of "joined events or system variables" with the transmitted event. This function does not wait.

By default, this condition will be checked immediately when the set of joined events is evaluated by [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) and may not wait for a value change. It is also possible to delay the checking of the condition until the next message with the given signal arrives.

## Parameters

- **aSignal**: Signal that should be awaited with a value outside the given range.
- **aEnvVar**: Environment variable that should be awaited with a value outside the given range.
- **aSysVar**: System variable that should be awaited with a value outside the given range. May also be a specific element of a variable of type struct or generic array.

  **Note**: Not available for a single element of a double or integer array.

- **aLowLimit**: Lower limit of the value.
- **aHighLimit**: Upper limit of the value.
- **waitForSignalUpdate**: Condition should be checked immediately when the set of joined events is evaluated by [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md), or condition should be checked when the next message with the given signal will arrive.

## Return Values

- **-3**: Join error.
- **-2**: Type of the system/environment variable is not valid – only float or integer are valid – or signal or system variable is not valid or invalid limits of the given range.
- **-1**: General error, for example, functionality is not available.
- **> 0**: Number of the joined event.

## Example

```c
// waits until the value of signal or system variable ‚Velocity’ is outside the given range
long result;
dword index = 0;
result = TestJoinSignalOutsideRange(Velocity, 30, 50);
// ... other join events
TestJoinEnvVarEvent(MyEnvVar);
TestJoinTextEvent("ErrorFrame occurred!");

index = TestWaitForAnyJoinedEvent(2000);
```

[TestWaitForSignalOutsideRange](CAPLfunctionTestWaitForSignalOutsideRange.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)