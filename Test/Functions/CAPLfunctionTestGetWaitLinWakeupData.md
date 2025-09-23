# TestGetWaitLinWakeupData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitLinWakeupData (linWakeupFrame apEvent); // form 1`
- `long TestGetWaitLinWakeupData (dword index, linWakeupFrame apEvent); // form 2`

## Description

If LIN Wakeup frame is the last event that triggers a wait instruction, the frame content can be called up with the first function.  
The second function can only be used for "joined events". The number of the "joined event" (return value of `testJoin...`) is here being used as an index.

## Parameters

- **apEvent**: Event variable that should be filled in with this function.
- **index**: Number of the "joined event" corresponds with the return value of `testJoin...`.

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not an awaited event

## Example

```plaintext
testcase tcTFS_linWakeupEvent ()
{
    linWakeupFrame linWakeupData;
    if (testWaitForLinWakeupFrame(5000) == 1)
    {
        if (testGetWaitLinWakeupData(linWakeupData) == 0)
        {
            testStep("Evaluation", "LIN Wakeup event occurred. Signal length is %d ns", linWakeupData.length_ns);
        }
    }
}
```

[TestWaitForLinWakeupFrame](CAPLfunctionTestWaitForLinWakeupFrame.md) • [TestJoinLinWakeupEvent](CAPLfunctionTestJoinLinWakeupEvent.md)
