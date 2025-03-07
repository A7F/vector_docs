[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitEventMostMsgData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitEventMostMsgData

# TestGetWaitEventMostMsgData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestGetWaitEventMostMsgData (mostMessage aMessage); // form 1`
- `long TestGetWaitEventMostMsgData (dword index, mostMessage aMessage); // form 2`

## Description

If the last event was a MOST message (MOST control message or MOST spy message) that resolved a wait construction, with the first function the content of the message can be called. The second function can only be used for "joined events". The number of the "joined event" (return value of "testJoin...") is here being used as an index.

## Parameters

- **aMessage**: Message variable that should be filled in with this function.
- **index**: Number of the "joined event" corresponds with the return value of "testJoin…".

## Return Values

- **0**: Successful data access.
- **-1**: Data access cannot be executed, the last event was no message event.

## Example

```plaintext
if(testWaitForMostMessage("AudioDiskPlayer.MediaInfo.Status", 1, 500) == 1)
{
    mostMessage * msg;
    testGetWaitEventMostMsgData(msg);
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

[TestWaitForMostMessage](CAPLfunctionTestWaitForMostMessage.md) • [TestWaitForMostReport](CAPLfunctionTestWaitForMostReport.md) • [TestJoinMostMessageEvent](CAPLfunctionTestJoinMostMessageEvent.md) • [TestJoinMostReportEvent](CAPLfunctionTestJoinMostReportEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)