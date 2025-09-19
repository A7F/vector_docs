[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetVlan.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethernetPacket::SetVlan**

# ethernetPacket::SetVlan

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Method Syntax

- `long ethernetPacket.SetVlan(word tpid, word tci); // form 1`
- `long ethernetPacket.SetVlan(dword vlanIndex, word tpid, word tci); // form 2`

## Description

Sets the VLAN tag of an Ethernet packet. If the packets do not contain a VLAN tag, a new VLAN tag is added. For double-tagged VLAN, form 2 can be used.

## Parameters

- **tpid**: VLAN TPDI value to set.
- **tci**: VLAN TCI value to set.
- **vlanIndex**: Index of the VLAN tag for double-tagged VLANs. Index 0 is the inner VLAN, index 1 the outer VLAN. Range: 0..2

## Return Values

- **0**: Success
- **1**: Failed to add VLAN tag

## Example

```plaintext
on key '1'
{
  ethernetPacket pkt;

  pkt.SetVlan( 0x8100, 0x5123 );

  output( pkt );
}

on key '2'
{
  ethernetPacket pkt;

  // double tagged VLAN
  pkt.SetVlan( 0, 0x8100, 0x5123 );
  pkt.SetVlan( 1, 0x88A8, 0x6456 );

  output( pkt );
}
```

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
