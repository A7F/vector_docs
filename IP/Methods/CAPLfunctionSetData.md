[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetData.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::SetData

# ethernetPacket::SetData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

- `word ethernetPacket.SetData(word offset, char source[], word length); // form 1`
- `word ethernetPacket.SetData(word offset, byte source[], word length); // form 2`
- `word ethernetPacket.SetData(word offset, struct * source); // form 3`
- `word ethernetPacket.SetData(word offset, sysvarStruct source); // form 4`
- `word ethernetPacket.SetData(char protocol[], char field[], char data[], word length); // form 5`
- `word ethernetPacket.SetData(char protocol[], char field[], byte data[], word length); // form 6`

## Description

Copies bytes from a char array, byte array, CAPL struct or system variable struct to the data of an Ethernet packet.

## Parameters

- **offset**: Byte offset of the data in the [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md). Offset 0 is the byte directly after the Ethertype.
- **source**: Source where the data is copied from.
- **length**: Number of bytes to copy.
- **protocol**: Name of the protocol.
- **field**: Name of the field.

## Return Values

Number of bytes copied to the [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md).

## Example

```plaintext
on key '1'
{
  _align(1) struct MyMsgLayout
  {
    word  valueA;
    dword valueB;
  };

  ethernetPacket pkt;
  struct MyMsgLayout myData;

  myData.valueA = 1;
  myData.valueB = 2;

  pkt.source      = ethGetMacAddressAsNumber( "20:00:00:00:00:01" );
  pkt.destination = ethGetMacAddressAsNumber( "FF:FF:FF:FF:FF:FF" );
  pkt.type        = 0xF123; // proprietary Ethertype
  pkt.Length      = __size_of(struct MyMsgLayout);
  pkt.SetData( 0, myData );

  output( pkt );
}
```

[See Also](javascript:void(0);)
