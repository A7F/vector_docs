[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinLinReceiveErrorEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinLinReceiveErrorEvent

# TestJoinLinReceiveErrorEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestJoinLinReceiveErrorEvent (dword aFrameId)
long TestJoinLinReceiveErrorEvent ()
```

## Description

Completes the current set of "joined events" with the transmitted event. This function does not wait.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aFrameId**: Numeric ID of a frame whose Receive Error should be awaited. Default value: wait for any ID.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```c
testcase tcTFS_waitForLINResponse(int frameId)
{
    long eventIndex;

    testJoinMessageEvent(frameId);
    testJoinLinReceiveErrorEvent(frameId);
    testJoinLinCSErrorEvent(frameId);
    testJoinLinTransmErrorEvent(frameId);

    eventIndex = testWaitForAnyJoinedEvent(5000);
    switch (eventIndex)
    {
        case 1: // valid frame
            testStepPass("Validation", "IUT has responded correctly");
            break;

        case 2:  // receive error
            testStepFail("Validation", "IUT has responded with wrong number of data bytes");
            break;

        case 3: // checksum error
            testStepFail("Validation", "IUT has responded with wrong checksum");
            break;

        case 4: // transmission error
            testStepFail("Validation", "IUT has not responded");
            break;
        default:
            testStepFail("Validation", "Internal error! Unexpected event (return code %d) on waiting for response", eventIndex);
    }
}
```

[TestGetWaitLinReceiveErrData](CAPLfunctionTestGetWaitLinReceiveErrData.md) • [TestWaitForLinReceiveError](CAPLfunctionTestWaitForLinReceiveError.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)