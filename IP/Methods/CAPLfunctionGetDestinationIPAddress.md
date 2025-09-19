[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetDestinationIPAddress.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethernetPacket::GetDestinationIPAddress**

# ethernetPacket::GetDestinationIPAddress

**Valid for**: CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long ethernetPacket.GetDestinationIPAddress( ip_Address address );
```

## Description

Assigns the destination IP address to an ip_Address variable.

**Note**: The ethernetPacket must contain [IPv4](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolIPv4.md) or [IPv6](../../../CANoeCANalyzer/Ethernet/Protocols/ProtocolIPv6.md) protocol. Use `ethernetPacket::<protocol>.IsAvailable()` before calling this method.

## Parameters

- **address**: IP address is assigned to this variable.

## Return Values

- **0**: success
- **-1**: No IPv4 or IPv6 protocol available in packet.

## Example

```plaintext
on ethernetPacket *
{
  // otherwise access ethernetPacket packet with packet.GetSourceIPAddress(addressSrc) ...
  ip_Address addressSrc, addressDst;
  char strAddressSrc[60], strAddressDst[60];

  this.GetSourceIPAddress(addressSrc);
  this.GetDestinationIPAddress(addressDst);
  addressSrc.PrintAddressToString(strAddressSrc);
  addressDst.PrintAddressToString(strAddressDst);
  write("from %s to %s", strAddressSrc, strAddressDst);
}
```

[See Also](javascript:void(0);)
