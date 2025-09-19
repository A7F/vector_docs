[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Selectors/CAPLfunctionProtocolByteLength.md)

# ethernetPacket Selectors: `<protocol>`.byteLength

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md) » Selector `<protocol>`.byteLength

**Valid for**: CANoe DE • CANoe4SW DE

## Selectors

```
dword ethernetPacket.<protocol>.byteLength;
```

## Description

Returns the length of the payload of the protocol. The selector is read only.

If `<protocol>` is not contained in the packet, the selector returns 0. [ethernetPacket::protocol::IsAvailable](../Methods/CAPLfunctionProtocolIsAvailable.md) can be used to find out if the protocol is available.

## Parameters

—

## Return Values

Length of the protocol payload in bytes.

## Example

```plaintext
ethernetPacket pkt;
word           offset, length, i;

// initialize packet with IPv4 and UDP protocols
pkt.udp.Init();
pkt.udp.ResizeData(10);

offset = pkt.udp.byteOffset;
length = pkt.udp.byteLength;

write( "Protocol udp is at byte %d:%d", offset, length );

for( i = 0; i < length; i++ )
{
    pkt.byte( offset+i ) = i;
}

// calculate UDP and IPv4 checksum and send Ethernet packet
pkt.CompletePacket();
output( pkt );
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
