[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinLinEtfSingleResponseEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinLinETFSingleResponseEvent

# TestJoinLinETFSingleResponseEvent

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestJoinLinETFSingleResponseEvent (dword aETFFrameId, dword aAssocFrameId)
```

## Description

Adds an event of type LIN Event-triggered Frame Single Response to the set of joined events. This is a non-blocking function.

**Note**

Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aETFFrameId**: Frame identifier of LIN event-triggered frame to be awaited.
- **aAssocFrameId**: Frame identifier of a LIN unconditional frame associated with the awaited event-triggered frame.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```c
testcase tcTFS_waitForLinETFSingleResponse(int etfFrameId)
{
    long eventIndex;
    testJoinLinETFSingleResponseEvent(etfFrameId, linGetProtectedID(0x36));
    testJoinLinETFSingleResponseEvent(etfFrameId, linGetProtectedID(0x34));

    eventIndex = testWaitForAnyJoinedEvent(5000);
    switch (eventIndex)
    {
        case 1:
            testStepPass("Validation", "ETF single frame response occurred. FrameId=0x36");
            break;

        case 2:
            testStepPass("Validation", "ETF single frame response occurred. FrameId=0x34");
            break;

        default:
            testStepFail("Validation", "ETF single frame response not occurred");
    }
}
```

[TestGetWaitLinETFSingleResponseData](CAPLfunctionTestGetWaitLinEtfSingleResponseData.md) • [TestWaitForLinETFSingleResponse](CAPLfunctionTestWaitForLinEtfSingleResponse.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md)
