[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Selectors/CAPLfunctionProtocolByteOffset.md)

# ethernetPacket Selectors: <protocol>.byteOffset

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md) » Selector <protocol>.byteOffset

**Valid for**: CANoe DE • CANoe4SW DE

## Selectors

Syntax: `dword ethernetPacket.<protocol>.byteOffset;`

## Description

Returns the byte-offset of the protocol payload within the Ethernet packet. The selector is read only.

Offset 0 is directly after the Ethertype.

If `<protocol>` is not contained in the packet, the selector returns 0.

[ethernetPacket::protocol::IsAvailable](../Methods/CAPLfunctionProtocolIsAvailable.md) can be used to find out if the protocol is available.

## Parameters

—

## Return Values

Byte-offset

## Example

```plaintext
ethernetPacket pkt;
word           offset, length, i;

// initialize packet with IPv4 and UDP protocols
pkt.udp.Init();
pkt.udp.ResizeData(10);

offset = pkt.udp.byteOffset;
length = pkt.udp.byteLength;

write ( "Protocol udp is at byte %d:%d", offset, length );

for( i = 0; i < length; i++ )
{
  pkt.byte( offset+i ) = i;
}

// calculate UDP and IPv4 checksum and send Ethernet packet
pkt.CompletePacket();
output( pkt );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)