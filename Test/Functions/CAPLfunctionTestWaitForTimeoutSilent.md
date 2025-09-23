# TestWaitForTimeoutSilent

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForTimeoutSilent

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
long TestWaitForTimeoutSilent(int64 aTimeout);
```

## Description

Waits until the expiration of the specified timeout time. The function does not write in the Test Feature Set report.

## Parameters

- **aTimeout**: Maximum time that should be waited [ms]. (Transmission of 0: no timeout controlling. In this function this results in a hang up of the test module)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout

## Example

```c
// waits for 3000 ms
long result;
result = TestWaitForTimeoutSilent(3000);
```
