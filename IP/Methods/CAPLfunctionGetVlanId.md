[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetVlanId.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::GetVlanId

# ethernetPacket::GetVlanId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

- `dword ethernetPacket.GetVlanId(); // form 1`
- `dword ethernetPacket.GetVlanId(dword vlanIndex); // form 2`

## Description

Returns the VLAN ID, if the Ethernet packet contains a VLAN tag. For double-tagged VLAN form 2 can be used to access a specific VLAN ID.

## Parameters

- **vlanIndex**: Index of the VLAN tag for double-tagged VLANs. Index 0 is the inner VLAN, index 1 the outer VLAN.  
  Range: 0..2

## Return Values

ID of the VLAN or 0xFFFF if no VLAN is available.

## Example

```plaintext
on ethernetPacket *
{
  if (this.hasVlan())
  {
    word vlanId;

    vlanId = this.GetVlanId();

    write( "Received Ethernet packet with VLAN ID %d", vlanId );
  }
}
```

[See Also](javascript:void(0);)
