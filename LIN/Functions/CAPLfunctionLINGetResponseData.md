[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetResponseData.md)

**CAPL Functions** » **LIN** » **linGetResponseData**

# linGetResponseData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword LinGetResponseData(linFrame frameObject);
```

## Description

Queries LIN frame response data for specified FrameId on certain LIN channel. The FrameId and desired LIN channel number are expected to be set in the LIN frame prior to calling this function. The frame length, databyte, and checksum byte values will be copied into corresponding fields of LIN frame object. Note, that in the case there is no response data for the specified FrameId no data is copied.

## Parameters

- **frameObject**: The data structure to be filled in. Note, that the following selectors have to be set prior to calling this function:
  - ID
  - MsgChannel

## Return Values

- Non-zero on success.
- Zero on failure or when there is no response data defined.
- The non-zero value in real mode is the initial and in simulated mode the actual response counter value.

## Example

```plaintext
on key 'a'
{
   linFrame 0x1 testMsg;
   testMsg.MsgChannel = 1;
   testMsg.ID = 0;
   if (LINGetResponseData(testMsg) > 0)
   {
      writelineex(1,1,"FrameId=%d Length=%d, 0x%X 0x%X 0x%X 0x%X 0x%X 0x%X 0x%X 0x%X;", testMsg.ID, testMsg.DLC,
      testMsg.byte(0), testMsg.byte(1), testMsg.byte(2), testMsg.byte(3), testMsg.byte(4), testMsg.byte(5), testMsg.byte(6), testMsg.byte(7));
   }
}
```

[linSetRespCounter](CAPLfunctionLINSetRespCounter.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
