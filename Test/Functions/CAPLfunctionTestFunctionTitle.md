# TestFunctionTitle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
The title must not contain parenthesis.

## Function Syntax

`TestFunctionTitle (char title[]);`

## Description

The title of a test function is acquired automatically from the test function name in the CAPL program. It can also be set explicitly with the help of this function. The function may only be called within a test function and relates then to the respective test function.

## Parameters

- **title**: Title of the test function.

## Return Values

—

## Example

```c
testfunction CheckLockingOnCrash ()
{
  TestFunctionTitle("Check unlock of central locking system on crash");
  // Initialization of signals
  $CrashDetected = 0;
  $LockState = Locked;
  TestWaitForTimeout(200);
}
```

[TestSequenceTitle](CAPLfunctionTestSequenceTtitle.md)
