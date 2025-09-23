# TestWaitForLinScheduleChange

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForLinScheduleChange(dword aTimeout);` // form 1
- `long TestWaitForLinScheduleChange(long aScheduleTable, dword aTimeout);` // form 2
- `long TestWaitForLinScheduleChange(long aScheduleTable, long aScheduleSlot, dword aTimeout);` // form 3

## Description

Waits until the LIN scheduler reaches the specified table and slot index. If no indices are specified, the function will resume on the next change of the current table or slot index.

Should the event not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aScheduleTable**: Zero-based index of the schedule table which should be awaited.
- **aScheduleSlot**: Zero-based index of the schedule table slot which should be awaited.

  **Note:** Waiting for a specific schedule table slot is not supported by network interfaces of the XL family. Thus the parameter **aScheduleSlot** must not be used for these interfaces.

- **aTimeout**: Maximum time that should be waited [ms]. (Transmission of 0: no timeout controlling).

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
testcase tc_WaitForLinScheduleChange()

{
  long result;

  // Waits until the scheduler reaches slot 1 of schedule table 1
  result = TestWaitForLinScheduleChange(1, 1, 5000);

  if (result != 1)
  {
    testStepFail("TestWaitForLinScheduleChange failed!");
    testCaseFail();
  }
}
```
