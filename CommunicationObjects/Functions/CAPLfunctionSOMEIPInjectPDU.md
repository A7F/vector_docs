[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionSOMEIPInjectPDU.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » SOMEIP_InjectPDU

# SOMEIP_InjectPDU (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long SOMEIP_InjectPDU(PDU pdu, long channel, IP_Endpoint srcIPEndpoint, IP_Endpoint dstIPEndpoint);
```

## Description

Injects the PDU into the [SOME/IP-Binding block](../../../CANoeCANalyzer/CommunicationConcept/CCObjects.md#BindingSOMEIP), where its then send.

## Parameters

- **pdu**: PDU which should be injected.
- **channel**: Channel of the network where the PDU should be injected.
- **srcIPEndpoint**: IP endpoint of the PDU sender.
- **dstIPEndpoint**: IP endpoint of the PDU receiver.

## Return Values

- **0**: Success
- **1**: Error in srcIPEndpoint
- **> 1**: Error – no distinct connection can be determined

## Example

```plaintext
on pdu *
{
  ip_endpoint srcEp, dstEp;
  ethernetPacket ethPkt;

  if (this.msgChannel == 2 && this.LongHeaderID!=0xFFFF8100)
  {
    GetEthernetPacket(this, ethPkt);
    if (ethPkt.hwPort == ethernetPort::Ethernet2::ReplayBlock_1)
    {
      GetPDUsTPSrcIPEndpoint(this, srcEp);
      GetPDUsTPDstIPEndpoint(this, dstEp);
      SOMEIP_InjectPDU(this, 1, srcEp, dstEp);
    }
  }
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [Abstract_UnsubscribeEvent](CAPLfunctionAbstractUnsubscribeEvent.md) • [SOMEIP_SubscribeEventGroup](CAPLfunctionSOMEIPSubscribeEventGroup.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)