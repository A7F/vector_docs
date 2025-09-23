# TestJoinJ1939PGEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinJ1939PGEvent (dbMsg aMessage)`
- `long TestJoinJ1939PGEvent (dword aPGN)`
- `long TestJoinJ1939PGEvent (dword aPGN, dword aSourceAddress, dword aDestinationAddress)`

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait. For waiting, either [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) should be used depending on the requirement.

To get the message content of a parameter group which triggered a wait condition you can use the function [TestGetWaitJ1939PGData](CAPLfunctionTestGetWaitJ1939PGData.md).

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message that should be awaited. Must be a J1939 parameter group.
- **aPGN**: Parameter Group Number (with data page) of the message that should be awaited.
- **aSourceAddress**: Source address of the message that should be awaited or 0xFFFFFFFF if source address is ignored.
- **aDestinationAddress**: Destination address of the message that should be awaited or 0xFFFFFFFF if destination address is ignored.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```c
// Wait until both parameter groups TSC1 and EEC1 are received and analyze its content.

pg TSC1 pgTSC1;
pg EEC1 pgEEC1;
long indexTSC1, indexEEC1;
long result;

// 1. define combination of waiting conditions
indexTSC1 = TestJoinJ1939PGEvent(TSC1);
indexEEC1 = TestJoinJ1939PGEvent(EEC1);

// 2. Wait for both parameter groups
result = TestWaitForAllJoinedEvents(2000);
if (result > 0)
{
  // 3. Put data of TSC1 to pgTSC1 and analyze content
  if (TestGetWaitJ1939PGData(indexTSC1, pgTSC1) == 0)
  {
    //4. Validate data of pgTSC1
    …
  }
  // 5. Put data of EEC1 to pgEEC1 and analyze content
  if (TestGetWaitJ1939PGData(indexEEC1, pgEEC1) == 0)
  {
    //4. Validate data of pgEEC1
    …
  }
}
else if (result == 0)
{
  TestStepFail("Validation", " EEC1 and TSC are not received within 2000 ms");
}
else
{
  TestStepFail ("Validation", " TestWaitForAllJoinedEvents failed with unexpecetd error %i", result);
}
```

[TestWaitForJ1939PG](CAPLfunctionTestWaitForJ1939PG.md) • [TestGetWaitJ1939PGData](CAPLfunctionTestGetWaitJ1939PGData.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)
