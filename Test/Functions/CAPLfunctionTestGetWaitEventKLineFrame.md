# TestGetWaitEventKLineFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TestGetWaitEventKLineFrame(BYTE bufferOut[], dword bufferLen);
long TestGetWaitEventKLineFrame(BYTE bufferOut[], dword bufferLen, int64 timeStampOut[]);
```

## Description

If a K-Line frame is the last event that triggers a wait instruction, the content can be called up with the first function. The second function allows to call the content and the end of byte time stamps.

## Parameters

- **bufferOut**: Byte data buffer of the frame.
- **bufferLen**: Size of the data buffer.
- **timeStampOut**: Buffer of the end of byte stamps.

## Return Values

On success a value greater 0, otherwise a value less than 0.

## Example

```plaintext
DiagRequest EcuIdentification_Read req;
int64 timeStamps[100];
BYTE buffer[100];
dword bufferLength = 6;
int i = 0;
long rc;

DiagSetTarget("DUT");
req.SendRequest();
if (1 == TestWaitForDiagKLineFrameTransmitted(5000))
{
    TestStepPass("Transmitted KLine frame.");
    rc = TestGetWaitEventKLineFrame(buffer, bufferLength, timeStamps);
    if (rc > 0)
    {
        TeststepPass("TestGetWaitEventKLineFrame returned with success.");
        for (i = 0; i < rc; ++i)
        {
            write( "TRANSMITTED FRAME: BYTE VALUE: 0x%x. TIMESTAMP [%.3f]", buffer[i], timeStamps[i]/1000000000.0);
        }
    }
}
else
{
    TestStepFail("No confirmation of transmitted K-Line frame.");
}

if (1 == TestWaitForDiagKLineFrameReceived(5000))
{
    TestStepPass("Received KLine frame.");
    rc = TestGetWaitEventKLineFrame(buffer, bufferLength, timeStamps);
    if (rc > 0)
    {
        TeststepPass("TestGetWaitEventKLineFrame returned with success.");
        for (i = 0; i < rc; ++i)
        {
            write( "RECEIVED FRAME: BYTE VALUE: 0x%x. TIMESTAMP [%.3f]", buffer[i], timeStamps[i]/1000000000.0);
        }
    }
}
else
{
    TestStepFail("No indication of received K-Line frame.");
}
```
