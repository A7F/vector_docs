[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinMessageEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinMessageEvent

# TestJoinMessageEvent

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinMessageEvent (dbMsg aMessage)`
- `long TestJoinMessageEvent (dword aMessageId)`

## Description

Completes the current set of "joined events" with the transmitted event. This function does not wait.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message that should be awaited.
- **aMessageId**: Numeric ID of the message for which should be waited.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```plaintext
// add msg event to the current set of "joined events" and fill the msg data to message ‘eventMessage’
dword index = 0;
TestJoinMessageEvent(VehicleMotion);
// ... other join events
TestJoinEnvVarEvent(MyEnvVar);
TestJoinSignalInRange(Velocity, 80, 100);
TestJoinTextEvent("ErrorFrame occurred!");

index = TestWaitForAnyJoinedEvent(2000);

TestGetWaitEventMsgData(index, eventMessage);
```

[TestWaitForMessage](CAPLfunctionTestWaitForMessage.md) • [TestGetWaitEventMsgData](CAPLfunctionTestGetWaitEventMsgData.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
