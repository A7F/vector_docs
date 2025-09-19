[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionProtocolFieldParseAddress.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::protocol::field::ParseAddress

# ethernetPacket::protocol::field::ParseAddress

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

`long ethernetPacket.<protocol>.<field>.ParseAddress( char addressAsString[] );`

## Description

Sets the protocol field, which has type IPv4 or IPv6 address.

The address must be given in

- IPv4 format for IPv4 address, i.e. `192.168.1.1`
- IPv6 format for IPv6 address, i.e. `FC00::0001:0002`

The method is only available for IPv4 or IPv6 address fields.

## Parameters

- **addressAsString**: Address in text form of format IPv4 or IPv6.

## Return Values

- **0**: Success
- **-1**: Error
- **-2**: Field or protocol not in packet
- **-4**: Invalid address format

## Example

```plaintext
ethernetPacket packet;
// ip_Address 255.255.255.255 addressDst

packet.ipv4.Init();
packet.ipv4.source.ParseAddress("198.128.1.81");
packet.ipv4.destination.ParseAddress("255.255.255.255");
//analog: packet.SetDestinationIPAddress(addressDst);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
