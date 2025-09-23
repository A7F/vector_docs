# TestGetWaitEventMsgData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitEventMsgData (message aMessage);`
- `long TestGetWaitEventMsgData (dword index, message aMessage);`
- `long TestGetWaitEventMsgData (linFrame aMessage);`
- `long TestGetWaitEventMsgData (dword index, linFrame aMessage);`
- `long TestGetWaitEventMsgData (gmLanMessage aMessage);`
- `long TestGetWaitEventMsgData (dword index, gmLanMessage aMessage);`
- `long TestGetWaitEventMsgData (a429word aMessage);`
- `long TestGetWaitEventMsgData (dword index, a429word aMessage);`

## Description

If a message event is the last event that triggers a wait instruction, the message content can be called up with the first function. The second function can only be used for "joined events". The number of the "joined event" (return value of `testJoin...`) is here being used as an index.

## Parameters

- **aMessage**: Message variable that should be filled in with this function.
- **index**: Number of the "joined event" corresponds with the return value of `testJoin...`.

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not a message event

## Example

```plaintext
// add msg event to the current set of "joined events" and fill the msg data to message ‘eventMessage’
dword index = 0;
TestJoinMessageEvent(VehicleMotion);
// ... other join events
index = TestWaitForAnyJoinedEvent(2000);

TestGetWaitEventMsgData(index, eventMessage);
```

[TestWaitForMessage](CAPLfunctionTestWaitForMessage.md) • [TestJoinMessageEvent](CAPLfunctionTestJoinMessageEvent.md)
