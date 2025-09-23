# TestWaitForLinETFSingleResponse

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestWaitForLinETFSingleResponse (dword aETFFrameId, dword aAssocFrameId, dword aTimeout);
```

## Description

Waits for the occurrence of a LIN Event-triggered frame with a single response for the specified associated frame. Should the event-triggered frame not occur before the expiration of the specified timeout, the wait condition is resolved nevertheless.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aETFFrameId**: Frame identifier of LIN event-triggered frame to be awaited.
- **aAssocFrameId**: Frame identifier of a LIN unconditional frame associated with the awaited event-triggered frame.
- **aTimeout**: Timeout in milliseconds.  
  Value 0: no timeout

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

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

[TestGetWaitLinETFSingleResponseData](CAPLfunctionTestGetWaitLinEtfSingleResponseData.md) • [TestJoinLinETFSingleResponseEvent](CAPLfunctionTestJoinLinEtfSingleResponseEvent.md)
