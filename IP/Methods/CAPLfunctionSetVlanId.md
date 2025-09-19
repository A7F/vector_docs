[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetVlanId.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::SetVlanId

# ethernetPacket::SetVlanId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

- `long ethernetPacket.SetVlanId(word vlanId); // form 1`
- `long ethernetPacket.SetVlanId(dword vlanIndex, word vlanId); // form 2`

## Description

Sets the VLAN ID of an Ethernet packet. If the packets do not contain a VLAN tag, a new VLAN tag is added. For double-tagged VLAN, form 2 can be used.

## Parameters

- **vlanId**: The VLAN ID to set.  
  Range: 0..0FFFh

- **vlanIndex**: Index of the VLAN tag for double-tagged VLANs. Index 0 is the inner VLAN, index 1 the outer VLAN.  
  Range: 0..2

## Return Values

- **0**: Success
- **1**: Failed to add VLAN tag
- **2**: VLAN ID out of range

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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
