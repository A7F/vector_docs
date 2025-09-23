# TestWaitForTextEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
long TestWaitForTextEvent(char aText[], dword aTimeout);
```

## Description

Waits for the signaling of the specified textual event from the individual test module. A signaling from another test module does not affect this wait instruction.

Should this event not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

## Parameters

- **aText**: Any (meaningful) textual event name
- **aTimeout**: Maximum time that should be waited [ms]  
  (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
// waits for the occurrence of text event "ErrorFrame occurred!"
long result;
result = TestWaitForTextEvent("ErrorFrame occurred!", 3000);

// handler 'on errorFrame' signals event
on errorFrame
{
   TestSupplyTextEvent("ErrorFrame occurred!");
}
```

[TestJoinTextEvent](CAPLfunctionTestJoinTextEvent.md) • [TestSupplyTextEvent](CAPLfunctionTestSupplyTextEvent.md)
