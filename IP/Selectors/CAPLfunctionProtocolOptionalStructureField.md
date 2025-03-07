[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Selectors/CAPLfunctionProtocolOptionalStructureField.md)

# ethernetPacket Selectors: <protocol>.<optional-structure>.<field>

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md) » Selector<protocol>.<optional-structure>. field

**Valid for**: CANoe DE • CANoe4SW DE

## Selectors

- `byte ethernetPacket.<protocol>.<optional-structure>.<field>;`
- `word ethernetPacket.<protocol>.<optional-structure>.<field>;`
- `dword ethernetPacket.<protocol>.<optional-structure>.<field>;`
- `qword ethernetPacket.<protocol>.<optional-structure>.<field>;`

## Description

Read or write access to protocol-option fields within optional-structures.

See protocol overview for protocol and field designators.

If `<protocol>`, `<optional-structure>` or `<field>` is not contained in the packet, the measurement is stopped with a runtime error. `ethernetPacket::<protocol>::<optional-structure>::IsAvailable` can be used to find out if the field is available.

The data type depends on the protocol field. The bit length is rounded up to next larger CAPL data type, i.e. a 4-bit protocol field will use byte and a 12-bit protocol field will use word.

This selector is available for protocol field of type integer. For protocol fields, which are not integer values, the method [GetData](../Methods/CAPLfunctionGetData.md) and [SetData](../Methods/CAPLfunctionSetData.md) can be used.

## Parameters

—

## Return Values

Value of the protocol field.

## Example

```plaintext
on key '1'
{
  ethernetPacket pkt;
  pkt.ipv6.Init(); // initialize a packet IPv6
  pkt.udp.Init(); // and UDP
  pkt.ipv6.fragment.Init();
  pkt.ipv6.fragment.offset = 100;
  pkt.ipv6.framgent.flag  = 1;
  pkt.ipv6.fragment.identification = 0x1234;
  pkt.CompletePacket();
  output( pkt );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)