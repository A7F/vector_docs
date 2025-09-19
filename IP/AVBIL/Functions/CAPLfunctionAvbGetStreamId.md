[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbGetStreamId.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **AvbGetStreamId**

# AvbGetStreamId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbGetStreamId(dword listenerOrTalkerHandle, byte retStreamId[]);
```

## Description

The function retrieves the Stream Identifier (ID) of the Listener or Talker.

## Parameters

- **listenerOrTalkerHandle**: The handle of the Listener or Talker.
- **retStreamId**: The 64 bitstream Identifier (ID) upon successful return of the function.

## Return Values

- **0**: The function completed successfully.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

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

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
