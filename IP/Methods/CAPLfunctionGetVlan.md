[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetVlan.md)

**CAPL Functions » Ethernet » Function Overview » ethernetPacket::GetVlan**

# ethernetPacket::GetVlan

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

- `long ethernetPacket.GetVlan(word &tpid, word &tci); // form 1`
- `long ethernetPacket.GetVlan(dword vlanIndex, word &tpid, word &tci); // form 2`

## Description

Returns the VLAN tag, if the Ethernet packet contains a VLAN tag.  
For double-tagged VLAN form 2 can be used to access a specific VLAN tag.

## Parameters

- **vlanIndex**: Index of the VLAN tag for double-tagged VLANs. Index 0 is the inner VLAN, index 1 the outer VLAN.  
  Range: 0..2
- **tpid**: Returns the VLAN TPDI value.
- **tci**: Returns the VALN TCI value.

## Return Values

- **0**: Success
- **1**: Packet does not contain VLAN
- **<0**: Internal error

## Example

```plaintext
on ethernetPacket *
{
  if (this.hasVlan())
  {
    word tpid, tci;

    if (this.GetVlan( tpid, tci ) == 0)
    {
      write( "Received Ethernet packet with VLAN TPID 0x%X TCI 0x%X", tpid, tci );
    }
  }
}
```

[See Also](javascript:void(0);)