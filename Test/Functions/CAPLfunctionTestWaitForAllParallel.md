# testWaitForAllParallel

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
long testWaitForAllParallel(dword timeout);
```

## Description

Waits until execution of all parallel threads finished. In case all threads already finished execution, the function returns instantly.

**Note**: Since neither the state nor the resources used by a parallel test thread are known at runtime, it is not aborted after a timeout and continues in the background. Otherwise crashes could occur leading to higher risks. This function can only be used in test units with report configured to use Test Report Viewer format.

## Parameters

- **timeout**: Maximum time to wait [ms]. Specify 0 to wait without timeout.

## Return Values

- **0**: Resume due to timeout.
- **1**: Resume due to thread finished.

## Example

```c
export testcase TestParallelExecution()
{
  write("Start parallel execution.");
  testStartParallel(ParallelFunction, 500);
  teststartParallel(ParallelFunctionTwo);

  testWaitForAllParallel(2000);

  write("End parallel execution");
}

testfunction ParallelFunction(dword aTimeout)
{
  testWaitForTimeout(aTimeout);
  write("Wait in parallel.");
}

testfunction ParallelFunctionTwo()
{
  testWaitForTimeout(400);
  write("Wait in parallel again.");
}
```
