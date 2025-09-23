# TestGetWaitLinETFSingleResponseData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestGetWaitLinETFSingleResponseData (linFrame apEvent);
long TestGetWaitLinETFSingleResponseData (dword index, linFrame apEvent);
```

## Description

If LIN Event-triggered frame with a single response for the specified associated frame is the last event that triggers a wait instruction, the event content can be called up with this function.

When the triggering event is a part of a wait instruction for joined events, the index parameter has to correspond to the return value of "testJoin..." function.

## Parameters

- **apEvent**: Event variable that is filled with current data from the bus.
- **index**: Index of the joined event. It corresponds to the return value of "testJoin..." function.

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not an awaited event

## Example

```c
testcase tcTFS_linETFSingleResponse ()
{
    linFrame 0 linETFSingleResponseData;
    if (testWaitForLinETFSingleResponse(0x3A, 0x36, 5000) == 1)
    {
        if (testGetWaitLinETFSingleResponseData(linETFSingleResponseData) == 0)
        {
            testStep("Evaluation", "LIN Event-triggered frame with a single response occurred for FrameId=0x%X", linETFSingleResponseData.ID);
        }
    }
}
```

[TestWaitForLinETFSingleResponse](CAPLfunctionTestWaitForLinEtfSingleResponse.md) • [TestJoinLinETFSingleResponseEvent](CAPLfunctionTestJoinLinEtfSingleResponseEvent.md)
