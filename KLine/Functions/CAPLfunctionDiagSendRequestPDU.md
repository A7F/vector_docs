[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionDiagSendRequestPDU.md)

**CAPL Functions** » **Diagnostics** » **DiagSendRequestPDU**

# DiagSendRequestPDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long DiagSendRequestPDU(BYTE rawPDU[], WORD rawPDULength)
```

## Description

Sends a raw byte buffer. Allows also to send invalid requests.

## Parameters

- **rawPDULength**: Length of the raw buffer
- **raw**: PDU Byte buffer.

## Return Values

On success 0, otherwise a value less than 0.

## Example

```c
BYTE request[5];
write ("EXECUTE: Send Tester Present request");
request[0] = 0x81;
request[1] = 0x12;
request[2] = 0xF1;
request[3] = 0x3E;
request[4] = 0xC2;
if (0 == DiagSendRequestPDU(request, elcount(request)))
{
    TestStepPass("Test DiagSendRequestPDU()", "Sending of raw request PDU reports OK.");
}
else
{
    TestStepFail("Test DiagSendRequestPDU()", "Sending of raw request PDU did not work!");
}
if (1 == TestWaitForDiagKLineFrameTransmitted(1000))
{
    TestStepPass("Raw request was sent");
}
else
{
    TestStepFail("Error sending raw request");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
