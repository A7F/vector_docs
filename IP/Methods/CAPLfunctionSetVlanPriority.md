[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetVlanPriority.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethernetPacket::SetVlanPriority**

# ethernetPacket::SetVlanPriority

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

- `long ethernetPacket.SetVlanPriority(word vlanPriority);` // form 1
- `long ethernetPacket.SetVlanPriority(dword vlanIndex, word vlanPriority);` // form 2

## Description

Sets the VLAN priority of an Ethernet packet. If the packets do not contain a VLAN tag, a new VLAN tag is added. For double-tagged VLAN, form 2 can be used.

## Parameters

- **vlanPriority**: The VLAN priority to set.  
  Range: 0..7

- **vlanIndex**: Index of the VLAN tag for double-tagged VLANs. Index 0 is the inner VLAN, index 1 the outer VLAN.  
  Range: 0..2

## Return Values

- **0**: Success
- **1**: Failed to add VLAN tag
- **2**: VLAN priority out of range

## Example

```plaintext
on key '1'
{
  ethernetPacket pkt;

  pkt.SetVlanId( 10 );
  pkt.SetVlanPriority( 1 );

  output( pkt );
}

on key '2'
{
  ethernetPacket pkt;

  // double tagged VLAN
  pkt.SetVlanId( 0, 10 );
  pkt.SetVlanPriority( 0, 1 );
  pkt.SetVlanId( 1, 20 );
  pkt.SetVlanPriority( 1, 2 );

  output( pkt );
}
```

[See Also](javascript:void(0);)