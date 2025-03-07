[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinLinHeaderEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinLinHeaderEvent

# TestJoinLinHeaderEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinLinHeaderEvent (dbMsg aFrame)`
- `long TestJoinLinHeaderEvent (dword aFrameId)`

## Description

Completes the current set of "joined events" with the transmitted event. This function does not wait.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aFrame**: Frame whose header should be awaited.
- **aFrameId**: Numeric ID of a frame whose header should be awaited.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```plaintext
testcase tcTFS_waitForLINHeader(int frameId)
{
    long eventIndex;

    testJoinLinHeaderEvent(frameId);
    testJoinLinWakeupEvent();
    testJoinLinSyncErrorEvent();

    eventIndex = testWaitForAnyJoinedEvent(5000);
    switch (eventIndex)
    {
        case 1:
            testStepPass("Validation", "LIN Header for FrameId=0x%X occurred", frameId);
            break;

        case 2:
            testStepFail("Validation", "LIN Wakeup signal occurred");
            break;

        case 3:
            testStepFail("Validation", "LIN Sync error occurred");
            break;

        default:
            testStepFail("Validation", "Internal error! Unexpected event (return code %d) on waiting for any LIN event", eventIndex);
    }
}
```

[TestGetWaitLinHdrData](CAPLfunctionTestGetWaitLinHdrData.md) • [TestWaitForLinHeader](CAPLfunctionTestWaitForLinHeader.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)