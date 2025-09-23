# TestGetWaitEventMostAMSMsgData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestGetWaitEventMostAMSMsgData (MostAMSmessage aMessage); // form 1`
- `long TestGetWaitEventMostAMSMsgData (dword index, MostAMSmessage aMessage); // form 2`

## Description

If the last event was a MOST AMS message that resolved a wait construction, with the first function the content of the message can be called. The second function can only be used for "joined events". The number of the "joined event" (return value of "testJoin…") is here being used as an index.

## Parameters

- **aMessage**: Message variable that should be filled in with this function.
- **index**: Number of the "joined event" corresponds with the return value of "testJoin...".

## Return Values

- **0**: Successful data access
- **-1**: Data access cannot be executed, the last event was no message event
- **-3**: aMessage is not long enough to store the data of the received message.

  **Remedy**: Explicit setting of a sufficient size when defining the variable, e.g. `mostAMSMessage * msg = {DLC = 2000};`

## Example

```plaintext
if(testWaitForMostAMSMessage("AudioDiskPlayer.MediaInfo.Status", 1, 500) == 1)
{
    mostAMSMessage * msg;
    testGetWaitEventMostAMSMsgData(msg);
    if(msg.DLC > 4 && msg.byte(4) == 1)
    {
        testStepPass("MediaType = Audio");
    }
    else
    {
        testStepFail();
    }
}
```

[TestWaitForMostAMSMessage](CAPLfunctionTestWaitForMostAMSMessage.md) • [TestWaitForMostAMSReport](CAPLfunctionTestWaitForMostAMSReport.md) • [TestJoinMostAMSMessageEvent](CAPLfunctionTestJoinMostAMSMessageEvent.md) • [TestJoinMostAMSReportEvent](CAPLfunctionTestJoinMostAMSReportEvent.md)
