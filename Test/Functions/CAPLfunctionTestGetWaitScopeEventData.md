# testGetWaitScopeEventData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long testGetWaitScopeEventData (ScopeEvent aScopeEvent);
```

## Description

Retrieves the data of Scope event triggered by the last wait instruction.

## Parameters

- **aScopeEvent**: Data structure to be filled.

## Return Values

- **0**: Data access successful.
- **-1**: Data access could not be executed, the last event was not an awaited event.

## Example

```c
void WaitForAnyScopeEvent(enum ScopeEventType expectedEventType)
{
    long res;
    int expected;
    int received;
    ScopeEvent scopeEventData;
    if ((res = testWaitForScopeEvent(8000)) != 1)
    {
        testStepFail("","testWaitForScopeEvent (any) failed res=%d", res);
        return;
    }
    res = testGetWaitScopeEventData(scopeEventData);
    if (res != 0)
    {
        testStepFail("","testGetWaitScopeEventData failed res=%d", res);
        return;
    }
    if (scopeEventData.Type != expectedEventType)
    {
        expected = expectedEventType;
        received = scopeEventData.Type;
        testStepFail("","testGetWaitScopeEventData delivers not expected event type: expected = %d, received = %d", expected, received);
        return;
    }
    testStepPass("", "Scope event received. Data: type=%d, DataId=%d, Time=%I64d", (int)scopeEventData.Type, (int)scopeEventData.DataID, scopeEventData.Time);
}
```

[Class ScopeEvent](../../Scope/Classes/CAPLfunctionsScopeEvent.md)
