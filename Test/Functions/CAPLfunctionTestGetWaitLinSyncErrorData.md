# TestGetWaitLinSyncErrorData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitLinSyncErrorData (LinSyncError apEvent); // form 1`
- `long TestGetWaitLinSyncErrorData (dword index, LinSyncError apEvent); // form 2`

## Description

Retrieves the data of a synchronisation error that triggered the last wait instruction.  
The second function can only be used for "joined events". The number of the "joined event" (return value of "testJoin...") is here being used as an index.

## Parameters

- **apEvent**: Data structure that will be filled with the synchronisation error data.
- **index**: Number of the "joined event" corresponds with the return value of "testJoin...".

## Return Values

- **0**: Data access was successful
- **-1**: Data access failed – the last wait function was not triggered by a synchronisation error

## Example

```plaintext
testcase tcTFS_linSyncErrorEvent ()
{
    linSyncError linSyncErrorData;
    if (testWaitForLinSyncError(5000) == 1)
    {
        if (testGetWaitLinSyncErrorData(linSyncErrorData) == 0)
        {
            testStep("Evaluation", "LIN Sync Error event occurred. SyncBreak=%d ns; SyncDel=%d ns", linSyncErrorData.breaklen, linSyncErrorData.delimiterlen);
        }
    }
}
```

[TestJoinLinSyncErrorEvent](CAPLfunctionTestJoinLinSyncErrorEvent.md) • [TestWaitForLinSyncError](CAPLfunctionTestWaitForLinSyncError.md)
