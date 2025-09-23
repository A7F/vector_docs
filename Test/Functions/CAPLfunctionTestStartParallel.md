# testStartParallel

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long testStartParallel(caplFunction, ...);
```

## Description

Spawns a new thread to execute the specified function. Execution will start as soon as possible.

**Note**

Since neither the state nor the resources used by a parallel test thread are known at runtime, it is not aborted after a timeout and continues in the background. Otherwise crashes could occur leading to higher risks. This function can only be used in test units with report configured to use Test Report Viewer format.

## Parameters

- **caplFunction**: CAPL function to execute in parallel. The function's parameters must be specified as parameters of the `testStartParallel` call in the correct order. The return value type of the function must be void.

## Return Values

- **0**: General error, e.g.: Functionality not available.
- **\> 0**: Handle of the new thread.

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
