# TestWaitForDiagChannelConnected

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForDiagChannelConnected(dword timeout_ms); // form 1`
- `long TestWaitForDiagChannelConnected(char ecuQualifier[], dword timeout_ms); // form 2`

## Description

Waits for the occurrence of the state change of a diagnostic channel to the state **Connected**. Should the connection not occur before the expiration of the time **timeout_ms**, the wait condition is resolved nevertheless.

## Parameters

- **timeout_ms**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.
- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
long status;
if (0 == DiagConnectChannel())
{
    TestStepPass("Channel connect called successfully.");
}
else
{
    TestStepFail("Channel connect returned with an error.");
    success = kRetFail;
}

status = TestWaitForDiagChannelConnected(2000);
if (1 == status)
{
    TestStepPass("Connected to target ECU");
}
else
{
    TestStepFail("Error connecting to target ECU");
}
```

[TestWaitForDiagChannelClosed](CAPLfunctionTestWaitForDiagChannelClosed.md)
