[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForLinSyncError.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForLinSyncError

# TestWaitForLinSyncError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestWaitForLinSyncError(dword aTimeout);
```

## Description

Waits for a synchronisation error for the specified amount of time.

## Parameters

- **aTimeout**: Timeout in milliseconds

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, e.g. functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
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

[TestGetWaitLinSyncErrorData](CAPLfunctionTestGetWaitLinSyncErrorData.md) • [TestJoinLinSyncErrorEvent](CAPLfunctionTestJoinLinSyncErrorEvent.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
