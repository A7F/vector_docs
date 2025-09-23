[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionProtocolIsAvailable.md)

# ethernetPacket::protocol::IsAvailable

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::protocol::IsAvailable

**Valid for**: CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long ethernetPacket.<protocol>.IsAvailable();
```

## Description

Checks if a protocol or protocol field is contained in the Ethernet packet.

## Parameters

—

## Return Values

- **1**: Ethernet packet contains the protocol
- **0**: Ethernet packet does not contain the protocol

## Example

```plaintext
on ethernetPacket *
{
  if (this.udp.IsAvailable())
  {
    write("Packet has UDP protocol with port %d to %d!", this.udp.source, this.udp.destination);
  }
}
```
