[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterGateway.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAdapterGateway

# IpGetAdapterGateway

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
The following signatures are deprecated (since 8.2 SP2)

## Function Syntax

- `long IpGetAdapterGateway( dword ifIndex, dword& ipv4address); // form 1`
- `long IpGetAdapterGateway( dword ifIndex, byte ipv6Address[]); // form 2`
- `long IpGetAdapterGateway( dword ifIndex, dword addressFamily , IP_Address address); // form 3`

## Description

The function retrieves the default gateway address associated with the specified network interface.

Gateway information is not yet available before the start of the measurement (on pre-start). Rather it is first available at the start of the measurement (on start) as soon as the stack has been completely initialized.

## Parameters

- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.
- **ipv4address**: The returned [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) gateway IPv4 address.
- **ipv6Address**: The local IPv6 address in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **count**: The size of the address array.
- **addressFamily**: The address family of the addresses, the address count will be returned. Possible values are:
  - 0: IPv4 address family, if available, else IPv6 family
  - 2: IPv4 address family
  - 28: IPv6 address family
- **address**: IP_Address variable where the address is copied to.

## Return Values

- **0**: The function completed successfully.
- **ERROR_NOT_ENOUGH_MEMORY (8)**: The address array was insufficient.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.
- **WSAEADDRNOTAVAIL (10049)**: No gateway address available.

## Example

```plaintext
on start
{
  long ifIdx;
  for( ifIdx = 1; ifIdx <= ipGetAdapterCount(); ifIdx++)
  {
    ip_Address gatewayAddress;
    if (ipGetAdapterGateway( ifIdx, 0, gatewayAddress ) == 0)
    {
      char gatewayStr[30];
      gatewayAddress.PrintAddressToString( gatewayStr );
      write( "%d. Adapter Gateway Address: %s", ifIdx, gatewayStr );
    }
  }
}
```
