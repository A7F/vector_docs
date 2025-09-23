# TestWaitForLinBitStreamStatus

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
long TestWaitForLinBitStreamStatus(dword awaitedStatus, dword timeout); // form 1
long TestWaitForLinBitStreamStatus(dword channel, dword awaitedStatus, dword timeout); // form 2
```

## Description

Waits until the sending of a LIN bitstream is started or stopped. The function will resume immediately if the transmission already has the awaited status.

Should the event not occur before the expiration of the time **timeout**, the wait condition is resolved nevertheless.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **awaitedStatus**
  - 0: Sending of the bitstream is stopped.
  - 1: Sending of the bitstream is started.

- **channel**
  - The LIN channel number which will be queried.

- **timeout**
  - Maximum time that should be waited [ms].
  - (Transmission of 0: no timeout controlling).

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
testcase tc_TestWaitForLinBitStreamStatus()
{
  long  result;

  // Wait for a maximum time of 100ms for the bitstream to start sending
  result = TestWaitForLinBitStreamStatus(1, 100);

  if(result != 1)
  {
    testStepFail("The sending of the bitstream didn't start within 100ms!");
    testCaseFail();
  }
}
```
