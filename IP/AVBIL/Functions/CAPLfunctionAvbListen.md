# AvbListen

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbListen(dword listenerHandle, char onListenCallback[]);
```

## Description

The function causes the Listener to listen for incoming connection requests, which will be provided in the CAPL callback [OnAvbListen](CAPLfunctionOnAvbListen.md) passed to this function.

The function simultaneously listens for incoming connection requests for streams propagated via the following transport protocols:

- AVTP
- RTP via UDP (*)
- RTSP via TCP (**) (only if property **RtspAddress** is set)

Incoming connection requests can be accepted with AvbAccept from inside the provided callback function [OnAvbListen](CAPLfunctionOnAvbListen.md).

## Parameters

- **listenerHandle**: The Listener handle.
- **onListenCallback**: The name of the CAPL callback function (see [OnAvbListen](CAPLfunctionOnAvbListen.md)).

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
