[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionProtocolGetData.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::protocol::GetData

# ethernetPacket::protocol::GetData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

- `word ethernetPacket.<protocol>.GetData( word offset, char[] dest, word length ); // from 1`
- `word ethernetPacket.<protocol>.GetData( word offset, byte[] dest, word length ); // from 2`
- `word ethernetPacket.<protocol>.GetData( word offset, struct * dest ); // from 3`
- `word ethernetPacket.<protocol>.GetData( word offset, sysvarStruct dest ); // from 4`

## Description

Gets payload data of a protocol within an Ethernet packet.

The data is copied to a destination buffer of the specified type. If the buffer is too small, the data is truncated.

If specified length is greater than available data, only the available data is copied to **dest** and the number of copied bytes is returned.

If `<protocol>` is not available in the packet, 0 is returned.

## Parameters

- **dest**: buffer where the data is copied to.
- **length**: Number of bytes to copy.
- **offset**: Byte offset in the payload where it starts to copy data.

## Return Values

Number of bytes copied to destination.

## Example

```plaintext
on ethernetPacket *
{
  _align(1) struct MyData
  {
    long value1;
    long value2;
  } buffer;

  if ((this.udp.IsAvailable()) && (this.udp.destination == 0xF123))
  {
    if (this.udp.GetData( 0, buffer ) == > 0)
    {
      write( "Value1=%d, Value2=%d", buffer.value1, buffer.value2 );
    }
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
