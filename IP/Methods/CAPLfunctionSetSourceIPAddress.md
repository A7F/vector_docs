[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetSourceIPAddress.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::SetSourceIPAddress

# ethernetPacket::SetSourceIPAddress

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long ethernetPacket.SetSourceIPAddress( ip_Address address );
```

## Description

Set source IP address of an ethernetPacket by an ip_Address variable.

**Note**: The ethernetPacket must contain [IPv4](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolIPv4.md) or [IPv6](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolIPv6.md) protocol.

## Parameters

- **address**: IP address is assigned to this variable.

## Return Values

- **0**: success
- **-1**: No IPv4 or IPv6 protocol available in packet.

## Example

```plaintext
ethernetPacket packet;
ip_Address 198.128.1.81 addressSrc;
ip_Address 255.255.255.255 addressDst;

packet.ipv4.Init();
packet.SetSourceIPAddress(addressSrc);
packet.SetDestinationIPAddress(addressDst);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
