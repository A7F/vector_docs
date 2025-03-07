[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionProtocolOptionalStructureInit.md)

## CAPL Functions » Ethernet » Function Overview » ethernetPacket::protocol::optional-structure::Init

### ethernetPacket::protocol::optional-structure::Init

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Method Syntax

`long ethernetPacket.<protocol>.<optional-structure>.Init();`

### Description

Add a protocol option for a specific protocol to the Ethernet packet. The protocol must support options. Following options are available:

- **IPv4**
  - End of Option list: `optionEOL`
  - No Operation: `optionNOP`
  - Security: `optionSecurity`
  - Loose Source Routing: `optionLooseSourceRoute`
  - Internet Timestamp: `optionTimeStamp`
  - Record Route: `optionRecordRoute`
  - Stream ID: `optionStreamID`
  - Strict Source Routing: `optionoptionStrictSourceRoute`

- **ICMPv4**
  - Address Mask Reply: `addrMaskReply`
  - Addr Mask Request: `addrMaskRequest`
  - Alternate Host Address: `alternateHostAddress`
  - Datagram Conv Error: `datagramConvError`
  - Destination Unreachable: `destinationUnreachable`
  - Domain Name Reply: `domainNameReply`
  - Domain Name Request: `domainNameRequest`
  - Echo: `echo`
  - Echo Reply: `echoReply`
  - Information Reply: `informationReply`
  - Information Request: `informationRequest`
  - IPv 6 I Am Here: `ipv6IAmHere`
  - IPv 6 Where Are You: `ipv6WhereAreYou`
  - Mobile Host Redirect: `mobileHostRedirect`
  - Mobile Reg Reply: `mobileRegReply`
  - Mobile Reg Request: `mobileRegRequest`
  - Msg Utilized by Exp: `msgUtilizedByExp`
  - Parameter Problem: `parameterProblem`
  - Redirect: `redirect`
  - Router Advertisement: `routerAdvertisement`
  - routerSolicitation: `routerSolicitation`
  - securityFailures: `securityFailures`
  - skip: `skip`
  - sourceQuench: `sourceQuench`
  - timeExceeded: `timeExceeded`
  - timestamp: `timestamp`
  - timestampReply: `timestampReply`
  - traceroute: `traceroute`

- **IPv6**
  - Hop-By-Hop Options: `hopByHopOptions`
  - Routing Header: `routing`
  - Fragment Header: `fragment`
  - Authentication Header: `authentication`
  - Encapsulating Security Payload: `esp`
  - Destination Options Header: `destinationOptions`

- **ICMPv6**
  - Destination Unreachable: `destinationUnreachable`
  - Echo Reply: `echoReply`
  - Echo Request: `echoRequest`
  - Home Agent Address Discovery Reply: `homeAgentAddrDiscReply`
  - Home Agent Address Discovery Request: `homeAgentAddrDiscRequest`
  - Mobile Prefix Advertisement: `mobilePrefixAdvertisement`
  - Mobile Prefix Solicitation: `mobilePrefixSolicitation`
  - Multicast Listener Done: `multicastListenerDone`
  - Multicast Listener Query: `multicastListenerQuery`
  - Multicast Listener Report: `multicastListenerReport`
  - Multicast Router Advertisement: `multicastRouterAdvertisement`
  - Multicast Router Solicitation: `multicastRouterSolicitation`
  - Multicast Router Termination: `multicastRouterTermination`
  - Parameter Problem: `parameterProblem`
  - timeExceeded: `timeExceeded`
  - v2MulticastListernerReport: `v2MulticastListernerReport`

- **NDP**
  - Inverse Advertisement: `inverseAdvertisement`
  - Inverse Solicitation: `inverseSolicitation`
  - Neighbor Advertisement: `neighborAdvertisement`
  - Neighbor Solicitation: `neighborSolicitation`
  - Redirect: `redirect`
  - routerAdvertisement: `routerAdvertisement`
  - Router Solicitation: `routerSolicitation`

- **IGMP**
  - Membership Query: `membershipQuery`
  - Membership Report: `membershipReport`

- **NTP**
  - Control: `control`

- **TFTP**
  - Acknowledge: `ack`
  - Error: `error`
  - File Data: `fileData`
  - Read Request: `readRequest`
  - Write Request: `writeRequest`

### Parameters

—

### Return Values

- **0**: Success
- **-1**: Error

### Example

```plaintext
on key '1'
{
  ethernetPacket pkt;
  pkt.ipv6.Init(); // initialize a packet IPv6
  pkt.udp.Init(); // and UDP
  pkt.ipv6.fragment.Init();
  pkt.ipv6.fragment.offset = 100;
  pkt.ipv6.framgent.flag  = 1;
  pkt.ipv6.fragment.identification = 0x1234;
  pkt.CompletePacket();
  output( pkt );
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)