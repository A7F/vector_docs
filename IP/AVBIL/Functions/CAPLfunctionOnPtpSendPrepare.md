# OnPtpSendPrepare

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long OnPtpSendPrepare( ethernetPacket * packet );
```

## Description

If the CAPL program implements this callback it is called right before a packet will be sent by the gPTP stack.

It is possible to manipulate the content of the packet or to block the sending of the packet on the network.

## Parameters

- **packet**: The [Ethernet packet](../../Objects/CAPLfunctionEthernetPacket.md) which will be sent.

## Return Values

- **0**: Block the Ethernet packet.
- **1**: Send the Ethernet packet.

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
- PtpSetProperty
- PtpSimulationTimespanFromPtpTimespan
- PtpTimeFromSimulationTime
- PtpTimeNow
