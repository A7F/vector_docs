[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionProtocolSetData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::protocol::SetData

# ethernetPacket::protocol::SetData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

- `word ethernetPacket.<protocol>.SetData( word offset, char[]data, word length ); // form 1`
- `word ethernetPacket.<protocol>.SetData( word offset, byte[]data, word length ); // form 2`
- `word ethernetPacket.<protocol>.SetData( word offset, struct * data); // form 3`
- `word ethernetPacket.<protocol>.SetData( word offset, sysvarStruct data); // form 4`
- `word ethernetPacket.<protocol>.SetData( char[]data, word length ); // form 5`
- `word ethernetPacket.<protocol>.SetData( byte[]data, word length ); // form 6`
- `word ethernetPacket.<protocol>.SetData( struct * data); form // 7`
- `word ethernetPacket.<protocol>.SetData( sysvarStruct data); form // 8`

## Description

Sets payload data of a protocol within an Ethernet packet.

If `<protocol>` is not available in the packet, no data is set and 0 is returned.

**For form 1-4 (with parameter offset):**

If the data is greater than the length of the Ethernet packet, the Ethernet packet is enlarged. If data is smaller as the current length of the payload the length is not changed.

**For form 5-8 (without parameter offset):**

The length of the data is resized to the given length of the new data.

## Parameters

- **data**: Buffer where the data is copied from.
- **length**: Number of bytes to copy to the protocol payload.
- **offset**: Byte offset in the payload where it starts to copy data.

## Return Values

Number of bytes copied to the Ethernet packet.

## Example

```plaintext
on key '1'
{
  ethernetPacket pkt;

  _align(1) struct MyData
  {
    long value1;
    long value2;
  } buffer;

  buffer.value1 = 1;
  buffer.value2 = 2;

  pkt.udp.Init();
  pkt.udp.SetData( 0, buffer );
  pkt.CompletePacket();
  output( pkt );
}
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
