[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionHasVlan.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::HasVlan

# ethernetPacket::HasVlan

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long ethernetPacket.HasVlan();
```

## Description

Returns number of VLAN tags.

## Parameters

—

## Return Values

Number of VLAN tags

## Example

```plaintext
on ethernetPacket *
{
  if (this.hasVlan())
  {
    word vlanId;

    vlanId = this.GetVlanId();

    write("Received Ethernet packet with VLAN ID %d", vlanId);
  }
}
```

[See Also](javascript:void(0);)