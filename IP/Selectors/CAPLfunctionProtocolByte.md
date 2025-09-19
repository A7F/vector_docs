[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Selectors/CAPLfunctionProtocolByte.md)

# ethernetPacket Selectors: `<protocol>`.byte/word/dword/qword/char/int/long/int64

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md) » Selector byte/word/dword/qword/char/int/long/int64

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Selectors

- `byte ethernetPacket.<protocol>.Byte(index);`
- `word ethernetPacket.<protocol>.Word(index);`
- `dword ethernetPacket.<protocol>.DWord(index);`
- `qword ethernetPacket.<protocol>.QWord(index);`
- `char ethernetPacket.<protocol>.Char(index);`
- `int ethernetPacket.<protocol>.Int(index);`
- `long ethernetPacket.<protocol>.Long(index);`
- `int64 ethernetPacket.<protocol>.Int64(index);`

## Description

Access to the payload of a protocol.

If index is greater than available data or `<protocol>` is not contained in the packet, the measurement is stopped with a runtime error. `ethernetPacket::protocol::IsAvailable` and `ethernetPacket::protocol::byteLength` can be used to find out if the data is available.

## Parameters

- **Index**: Byte offset. Index 0 is the first byte within the payload of the protocol. If index is greater than `ethernetPacket.<protocol>.byteLength` a runtime error occurs.

## Return Values

Value at specified index.

## Example

```plaintext
on ethernetPacket *
{
  if ((this.udp.IsAvailable()) && (this.udp.byteLength >= 16))
  {
    word val;
    val = this.udp.Word(15);
  }
}
on key '1'
{
  int i;
  ethernetPacket pkt;

  // initialize packet with IPv4 and UDP protocols
  pkt.udp.Init();

  // set IPv4 addresses
  pkt.ipv4.source.ParseAddress("192.168.1.1");
  pkt.ipv4.destination.ParseAddress("192.168.1.255");

  // set UDP ports
  pkt.udp.source = 40001;
  pkt.udp.destination = 40002;

  // set UDP payload
  pkt.udp.ResizeData(10);

  for(i = 0; i < 10; i++)
  {
    pkt.udp.Byte(i) = i;
  }

  // calculate UDP and IPv4 checksum and send Ethernet packet
  pkt.CompletePacket();
  output(pkt);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)