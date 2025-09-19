[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinLinCsErrorEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinLinCSErrorEvent

# TestJoinLinCSErrorEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinLinCSErrorEvent()`
- `long TestJoinLinCSErrorEvent(dbMsg apDBMsg)`
- `long TestJoinLinCSErrorEvent(dword aFrameId)`

## Description

Adds an event of type checksum error to the set of joined events. This is a non-blocking function.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **apDBMsg**: Symbolic message
- **aFrameId**: Frame identifier

## Return Values

- **-3**: Error while adding the specified event to the set of joined events
- **-1**: General error, e.g. functionality is not available
- **> 0**: Number of the newly joined event

## Example

```plaintext
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

[TestGetWaitLinCSErrorData](CAPLfunctionTestGetWaitLinCsErrData.md) • [TestWaitForLinCSError](CAPLfunctionTestWaitForLinCsError.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
