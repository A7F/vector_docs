[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbGetLastErrorText.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **AvbGetLastErrorText**

# AvbGetLastErrorText

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbGetLastErrorText(dword bufferLength, char buffer[]);
```

## Description

Function to retrieve the last error which occurs in the AVB IL as string.

The call of the `AvbGetLastErrorText` function does not reset the saved error text.

## Parameters

- **bufferLength**: Number of characters.
- **buffer**: Buffer receiving the error text.

## Return Values

Number of copied characters.

## Example

```c
char buffer[1024];
dword listenerHandle;

// open a listener
listenerHandle = AvbOpenListener();

// check if last function was executed successfully
if ((AvbGetLastErrorText(elcount(buffer), buffer)) != 0)
{
  write("AVB IL error occurred: %s", buffer);
}
```

[See Also](javascript:void(0);)
- AvbAccept
- AvbCloseListener
- AvbCloseTalker
- AvbConnect
- AvbGetLastError
- AvbGetLastErrorText
- AvbGetMediaType
- AvbGetProtocol
- AvbGetStreamId
- AvbGetStreamSourceAddress
- AvbGetStreamUniqueId
- AvbILControlInit
- AvbILControlResume
- AvbILControlStart
- AvbILControlStop
- AvbILControlWait
- AvbListen
- AvbOpenListener
- AvbOpenTalker
- AvbReceive
- AvbSend
- AvbSetMediaType
- AvbSetProperty
- AvbSetProtocol
- AvbSetVerbosity
- OnAvbConnect
- OnAvbListen
- OnAvbReceive
- OnAvbSend
- OnAvbSendPrepare
- OnPtpSendPrepare
- PtpSetProperty
- PtpSimulationTimespanFromPtpTimespan
- PtpTimeFromSimulationTime
- PtpTimeNow

---

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)