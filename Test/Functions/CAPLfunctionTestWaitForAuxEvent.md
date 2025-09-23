# TestWaitForAuxEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
long TestWaitForAuxEvent(dword aAuxEventId, dword aTimeout);
```

## Description

Waits for the signaling of the specified auxiliary event from a connected NodeLayer module.

Should the event not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

## Parameters

- **aAuxEventId**: Numeric event ID as it is returned on the creation of a check, for example.
- **aTimeout**: Maximum time that should be waited [ms]  
  (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
// wait is resumed on check event
long result;
checkId = ChkStart_Timeout(1000);
result = TestWaitForAuxEvent(checkId, 2000);
```

[TestJoinAuxEvent](CAPLfunctionTestJoinAuxEvent.md)
