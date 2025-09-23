# TestJoinDiagResponseFromEcu

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinDiagResponseFromEcu();` // form 1
- `long TestJoinDiagResponseFromEcu( char ecuQualifier[]);` // form 2

## Description

Adds an event of type diagnostic response reception to the set of joined events. This is a non-blocking function.

**Note**: Please be aware that the tester will only receive responses from the selected ECU target! Therefore if an event for ECU1 is added to the set of joined events, but ECU2 is set as target before the response from ECU1 arrives, the response from ECU1 will NOT be processed, i.e. the wait function does not continue. If the test program should continue on the reception of diagnostic responses from several ECUs at the same time, a physical or functional network description has to be the active diagnostic target!

## Parameters

- **ecuQualifier**: If given, only a response from the indicated ECU will fire the event.

## Return Values

Number of conditions in stock:

- **-3**: Error while adding the specified event to the set of joined events.
- **-1**: General error, for example, functionality is not available.
- **\> 0**: Number of the newly joined event.

[Error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```c
// waits for a diagnostic response
// wait is resumed on check event
dword index = 0;

TestJoinDiagResponseFromEcu();
// … other join events
TestJoinEnvVarEvent(MyEnvVar);
TestJoinSignalInRange(Velocity, 80, 100);
TestJoinTextEvent("ErrorFrame occurred!");

Index = TestWaitForAnyJoinedEvent(2000);
```

[TestWaitForDiagResponse](CAPLfunctionTestWaitForDiagResponse.md)
