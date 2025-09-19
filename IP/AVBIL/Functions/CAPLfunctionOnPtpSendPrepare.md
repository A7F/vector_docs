[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionOnPtpSendPrepare.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **OnPtpSendPrepare**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
