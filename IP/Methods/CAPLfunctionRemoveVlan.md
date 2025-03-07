[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionRemoveVlan.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::RemoveVlan

# ethernetPacket::RemoveVlan

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

- `long ethernetPacket.RemoveVlan();` // form 1
- `long ethernetPacket.RemoveVlan(dword vlanIndex);` // form 2

## Description

Removes a VLAN tag from an Ethernet packet. To remove a specific VLAN tag from a double-tagged packet form 2 can be used.

## Parameters

- **vlanIndex**: Index of the VLAN tag for double-tagged VLANs. Index 0 is the inner VLAN, index 1 the outer VLAN. Range 0..2

## Example

```plaintext
on ethernetPacket *
{
  if ((this.hasVlan()) && (this.msgChannel == 1))
  {
    ethernetPacket forwardPkt;

    forwardPkt = this;
    forwardPkt.msgChannel = 2;
    forwardPkt.RemoveVlan();

    output(forwardPkt);
  }
}
```

[See Also](javascript:void(0);)