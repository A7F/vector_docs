[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForParallel.md)

## CAPL Functions » Test Feature Set » testWaitForParallel

### Valid for: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

- `long testWaitForParallel(long handle, dword timeout); // form 1`
- `long testWaitForParallel(long handles[], dword timeout) // form 2`

### Description

Waits until execution of the thread specified via the handle parameter has finished. In case the thread already finished execution, the function returns instantly.

**Note**: Since neither the state nor the resources used by a parallel test thread are known at runtime, it is not aborted after a timeout and continues in the background. Otherwise crashes could occur leading to higher risks. This function can only be used in test units with report configured to use Test Report Viewer format.

### Parameters

- **handle**: Handle of the thread to wait for.
- **handles[]**: Handles of the threads to wait for.
- **timeout**: Maximum time to wait [ms]. Specify 0 to wait without timeout.

### Return Values

- **-3**: Resume due to error on handle list.
- **0**: Resume due to timeout.
- **>0**: Handle of the last finished parallel thread.

### Example

```plaintext
export testcase TestParallelExecution()
{
  dword handle1;
  write("Start parallel execution.");
  handle1 = testStartParallel(ParallelFunction, 500);
  testStartParallel(ParallelFunctionTwo);

  testWaitForParallel(handle1, 2000);

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
