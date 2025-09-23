[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionProtocolOptionalStructureClear.md)

## CAPL Functions » Ethernet » Function Overview » ethernetPacket::protocol::optional-structure::Clear

### ethernetPacket::protocol::optional-structure::Clear

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Method Syntax

`long ethernetPacket.<protocol>.<optional-structure>.Clear();`

### Description

Removes a protocol option from the Ethernet packet.

### Parameters

—

### Return Values

- **0**: Success
- **-1**: Error

### Example

```plaintext
on ethernetPacket msgChannel1.*
{
  if (this.ipv6.fragment.IsAvailable()
  {
    ethernetPacket pkt;

    // copy packet
    pkt            = this;
    pkt.msgChannel = 2;

    // remove option fragment
    pkt.ipv6.fragment.Clear();

    // recalculate checksums and output packet
    pkt.CompletePacket();
    output( pkt )
  }
}
```
