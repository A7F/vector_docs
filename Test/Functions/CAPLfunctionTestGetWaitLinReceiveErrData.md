# TestGetWaitLinReceiveErrData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitLinReceiveErrData (linReceiveError apEvent); // form 1`
- `long TestGetWaitLinReceiveErrData (dword index, linReceiveError apEvent); // form 2`

## Description

If LIN Receive Error event is the last event that triggers a wait instruction, the error content can be called up with the first function.  
The second function can only be used for "joined events". The number of the "joined event" (return value of `testJoin...`) is here being used as an index.

## Parameters

- **apEvent**: Event variable that should be filled in with this function.
- **index**: Number of the "joined event" corresponds with the return value of `testJoin...`.

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not an awaited event

## Example

```plaintext
testcase tcTFS_linReceiveErrorEvent ()
{
    linReceiveError linReceiveErrorData;
    if (testWaitForLinReceiveError(5000) == 1)
    {
        if (TestGetWaitLinReceiveErrData(linReceiveErrorData) == 0)
        {
            testStep("Evaluation", "LIN Receive Error event occurred for FrameId=0x%X", linReceiveErrorData.ID);
        }
    }
}
```

[TestWaitForLinReceiveError](CAPLfunctionTestWaitForLinReceiveError.md) • [TestJoinLinReceiveErrorEvent](CAPLfunctionTestJoinLinReceiveErrorEvent.md)
