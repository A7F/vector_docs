[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetVlanPriority.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::GetVlanPriority

# ethernetPacket::GetVlanPriority

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

- `dword ethernetPacket.GetVlanPriority(); // form 1`
- `dword ethernetPacket.GetVlanPriority(dword vlanIndex); // form 2`

## Description

Returns the VLAN priority, if the Ethernet packet contains a VLAN tag. For double-tagged VLAN form 2 can be used to access a specific VLAN priority.

## Parameters

- **vlanIndex**: Index of the VLAN tag for double-tagged VLANs. Index 0 is the inner VLAN, index 1 the outer VLAN.  
  Range: 0..2

## Return Values

Priority of the VLAN or 0xFFFF if no VLAN is available.

## Example

```plaintext
on ethernetPacket *
{
  if (this.hasVlan())
  {
    word vlanPrio;

    vlanPrio = this.GetVlanPriority();

    write("Received Ethernet packet with VLAN priority %d", vlanPrio);
  }
}
```

[See Also](javascript:void(0);)
