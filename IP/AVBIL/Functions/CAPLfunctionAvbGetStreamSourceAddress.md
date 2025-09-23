# AvbGetStreamSourceAddress

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbGetStreamSourceAddress(dword listenerOrTalkerHandle, byte retStreamSourceAddress[]);
```

## Description

The function retrieves the stream’s Source Address of the Listener or Talker. This usually is a 48 bit MAC address defining the sourcing system of the stream and is part of the Stream Identifier (ID).

**Note**: This address is not the source MAC address of the Ethernet layer.

## Parameters

- **listenerOrTalkerHandle**: The handle of the Listener or Talker.
- **retStreamSourceAddress**: The 48 bit bitstream Source Address upon successful return of the function.

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
