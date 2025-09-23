# TestGetWaitEventMostRawMsgData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long TestGetWaitEventMostRawMsgData(mostRawMessage aRawMsg);
long TestGetWaitEventMostRawMsgData(dword aIndex, mostRawMessage aRawMessage);
```

## Description

If the last (single) wait condition was resolved by a MOST control message, the function copies the data of that message into the provided CAPL variable.

The second signature can only be used for "joined events". The number of the "joined event" (return value of "testJoin...") is here being used as an index.

**Note:** If the wait condition was resolved by a control message having function catalog format, it is recommended to use [TestGetWaitEventMostMsgData](CAPLfunctionTestGetWaitEventMostMsgData.md) instead.

## Parameters

- **aMessage**: Message variable that should be filled with this function.
- **aIndex**: Number of the "joined event" that was resumed by a MOST (raw) control message. The number corresponds to return value of the "testJoin..." function call, by which the event was added to a joined condition.

## Return Values

- **0**: Successful data access
- **-1**: Data access can’t be executed, since the last wait condition was not resolved by a MOST message event.

## Example

—

[TestWaitForMostRawSpyMessage](CAPLfunctionTestWaitForMostRawSpyMessage.md) • [TestSendMostRawMessage](CAPLfunctionTestSendMostRawMessage.md)
