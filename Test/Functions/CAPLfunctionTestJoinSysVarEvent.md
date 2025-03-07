[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinSysVarEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinSysVarEvent

# TestJoinSysVarEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestJoinSysVarEvent(sysvar aSysVar)
```

## Description

Completes the current set of "joined events" with the transmitted event. This function does not wait.

## Parameters

- **aSysVar**: System variable that should be awaited. May also be a specific element of a variable of type struct or generic array.

  **Note**: Not available for a single element of a double or integer array.

## Return Values

- **-3**: Join error.
- **-1**: General error, for example, functionality is not available.
- **> 0**: Number of the joined event.

## Example

```c
// add sysVar event to the current set of "joined events" and get the sysVar value
dword index = 0;
float sysValue = 0;
TestJoinSysVarEvent(MySysVar);
// … other join events
TestJoinEnvVarEvent(MyEnvVar);
TestJoinSignalInRange(Velocity, 80, 100);
TestJoinTextEvent("ErrorFrame occurred!");
index = TestWaitForAnyJoinedEvent(2000);

TestGetWaitEventSysVarData(index, sysValue);
```

[TestWaitForSysVar](CAPLfunctionTestWaitForSysVar.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)