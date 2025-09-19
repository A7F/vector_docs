[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetSourceIPEndpoint.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::SetSourceIPEndpoint

# ethernetPacket::SetSourceIPEndpoint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long ethernetPacket.SetSourceIPEndpoint( ip_Endpoint endpoint );
```

## Description

Set source IP address and UDP/TCP port number of ethernetPacket by an ip_Endpoint.

**Note**: The ethernetPacket must contain [IPv4](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolIPv4.md) or [IPv6](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolIPv6.md) protocol and [UDP](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolUDP.md) or [TCP](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolTCP.md) protocol.

## Parameters

- **endpoint**: IP address and port.

## Return Values

- **0**: success
- **-1**: No IPv4 or IPv6 protocol available in packet.
- **-2**: No UDP or TCP protocol available in packet.

## Example

```plaintext
ethernetPacket packet;
ip_Endpoint 198.128.1.81:203    endpointSrc;
ip_Endpoint 255.255.255.255:204 endpointDst;

packet.tcp.Init();
packet.SetSourceIPEndpoint(endpointSrc);
packet.SetDestinationIPEndpoint(endpointDst);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
