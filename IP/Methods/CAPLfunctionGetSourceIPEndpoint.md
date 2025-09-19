[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetSourceIPEndpoint.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::GetSourceEndpoint

# ethernetPacket::GetSourceEndpoint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long ethernetPacket.GetSourceIPEndpoint( ip_Endpoint endpoint );
```

## Description

Assigns the source IP address and UDP/TCP port number to an ip_Endpoint variable.

**Note**: The ethernetPacket must contain [IPv4](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolIPv4.md) or [IPv6](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolIPv6.md) protocol and [UDP](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolUDP.md) or [TCP](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolTCP.md) protocol. If it does not contain the expected protocols, use `ethernetPacket::<protocol>.IsAvailable()` before calling this method.

## Parameters

- **endpoint**: IP address and port is assigned to this variable.

## Return Values

- **0**: success
- **-1**: No IPv4 or IPv6 protocol available in packet.
- **-2**: No UDP or TCP protocol available in packet.

## Example

```plaintext
on ethernetPacket *
{
  // otherwise access ethernetPacket packet with packet.GetSourceIPEndpoint(endpointSrc) ...
  ip_Endpoint endpointSrc, endpointDst;
  char strEndpointSrc[60], strEndpointDst[60];

  this.GetSourceIPEndpoint(endpointSrc);
  this.GetDestinationIPEndpoint(endpointDst);
  endpointSrc.PrintEndpointToString(strEndpointSrc);
  endpointDst.PrintEndpointToString(strEndpointDst);
  write("from %s to %s", strEndpointSrc, strEndpointDst);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
