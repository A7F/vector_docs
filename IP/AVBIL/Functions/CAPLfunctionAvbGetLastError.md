[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbGetLastError.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **AvbGetLastError**

# AvbGetLastError

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbGetLastError();
```

## Description

This function can be used to check whether the last called function of AVB IL has been successfully executed. The call of this function does not reset the saved error.

In the event of an error, a detailed error description can be read out using the [AvbGetLastErrorText](CAPLfunctionAvbGetLastErrorText.md) function.

## Parameters

—

## Return Values

- **0**: The last called function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

```c
dword retVal;
dword listenerHandle;

// open a listener
listenerHandle = AvbOpenListener();

// check if last function was successfully executed
if ((retVal = AvbGetLastError()) != 0)
{
  write("AVB IL error occurred: Error code: %d", retVal);
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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
