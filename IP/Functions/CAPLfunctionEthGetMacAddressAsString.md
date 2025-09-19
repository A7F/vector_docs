# ethGetMacAddressAsString

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetMacAddressAsString.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » ethGetMacAddressAsString

## Function Syntax

```plaintext
long ethGetMacAddressAsString( qword macAddr, char buffer[], dword bufferLength );
```

## Description

Converts a MAC address from qword to string. The function is helpful with [ethernetPacket.source](../Objects/CAPLfunctionEthernetPacket.md) and [ethernetPacket.destination](../Objects/CAPLfunctionEthernetPacket.md).

## Parameters

- **macAddr**: MAC address as qword, i.e. from ethernetPacket.source.
- **buffer**: Buffer where the MAC address string is copied to.
- **bufferLength**: Length of buffer

## Return Values

- **0**: The function completed successfully.
- **8**: The address buffer was insufficient.

## Example

```plaintext
on ethernetPacket *
{
  char macAddrStr[18];
  if (ethGetMacAddressAsString(this.source, macAddrStr, elcount(macAddrStr)) == 0)
  {
    write("Received Ethernet packet from %s", macAddrStr);
  }
}
```

[See Also](javascript:void(0);)
