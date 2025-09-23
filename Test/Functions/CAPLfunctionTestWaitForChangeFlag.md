# TestWaitForChangeFlag

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestWaitForChangeFlag(valueHandle * value, dword timeoutMs);
```

## Description

Waits for the change flag of a **valueHandle** to be set. Each valueHandle has a change flag which is set when the value changes and reset through an explicit call to [valueHandle::ClearChangeFlag](../../CommunicationObjects/Methods/CAPLfunctionValueClearChangeFlag.md) or [valueHandle::ResetValueState](../../CommunicationObjects/Methods/CAPLfunctionValueResetValueState.md).

Use this function instead of [TestWaitForChange](CAPLfunctionTestWaitForChange.md) if an undetermined number of changes may occur between a point where you reset the flag and a point where at least one change must have occurred.

In case of a distributed object, this functionality is only available if the `[EnableChangeInfo]` attribute is enabled for the respective object.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **timeoutMS**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred (change flag was set)

## Example

```c
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);
anEvent.ClearChangeFlag();
// ...
ret = testWaitForChangeFlag(anEvent, 200);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [TestWaitForChange](CAPLfunctionTestWaitForChange.md) • [TestWaitForUpdate](CAPLfunctionTestWaitForUpdate.md) • [TestWaitForUpdateFlag](CAPLfunctionTestWaitForUpdateFlag.md)
