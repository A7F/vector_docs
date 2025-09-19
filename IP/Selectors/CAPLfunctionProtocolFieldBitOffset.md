[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Selectors/CAPLfunctionProtocolFieldBitOffset.md)

# ethernetPacket Selectors: `<protocol>.<field>.bitOffset`

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md) » Selector <protocol>.<field>.bitOffset

**Valid for:** CANoe DE • CANoe4SW DE

## Selectors

```
dword ethernetPacket.<protocol>.<field>.bitOffset;
```

## Description

Bit offset of a protocol field. The selector is read only.

Offset 0 is directly after the Ethertype.

If `<protocol>` or `<field>` is not contained in the packet, the selector returns 0. [ethernetPacket::protocol::field::IsAvailable](../Methods/CAPLfunctionProtocolFieldIsAvailable.md) can be used to find out if the field is available.

## Parameters

—

## Return Values

Bit-offset of the protocol field.

## Example

```c
ethernetPacket pkt;
word offset, length;

// initialize packet with IPv4 and UDP protocols
pkt.udp.Init();
pkt.udp.ResizeData(10);

offset = pkt.udp.checksum.bitOffset;
length = pkt.udp.checksum.bitLength;

write("Protocol field udp.checksum is at bit %d:%d", offset, length);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)