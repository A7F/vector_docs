[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionProtocolResizeData.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethernetPacket::protocol::ResizeData**

# ethernetPacket::protocol::ResizeData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long ethernetPacket.<protocol>.ResizeData( word newLength );
```

## Description

Resizes the payload of a protocol within an Ethernet packet.

- If the **newLength** is greater than the length of the Ethernet packet, the Ethernet packet is enlarged.
- If `<protocol>` is not available in the packet, an error is returned.

## Parameters

- **newLength**: New length in bytes

## Return Values

- **0**: Success
- **-1**: Error
- **-2**: Field or protocol not in packet
- **-3**: Protocol has no payload to resize

## Example

```plaintext
word i;
ethernetPacket pkt;

pkt.udp.Init();
pkt.udp.ResizeData( 200 );

for (i = 0; i < 200; i++ )
{
  pkt.udp.Byte(i) = 0;
}

pkt.CompletePacket();
output( pkt );
```
