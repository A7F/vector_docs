[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpGetSocketName.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetSocketName

# IpGetSocketName

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long IpGetSocketName( dword socket, dword &ipv4Address, dword &port); // form 1`
- `long IpGetSocketName( dword socket, byte ipv6Address[], dword &port); // form 2`
- `long IpGetSocketName( dword socket, IP_Endpoint localEndpoint ); // form 3`

## Method Syntax

- `socket.GetSocketName(dword &ipv4Address, dword &port); // form 1`
- `socket.GetSocketName(byte ipv6Address[], dword &port); // form 2`
- `socket.GetSocketName(IP_Endpoint localEndpoint); // form 3`

## Description

The function returns the local bound address and port of a socket.

## Parameters

- **socket**: The socket handle.
- **ipv4Address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 address is returned in this variable.
- **Ipv6Address**: A [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) to return the IPv6 address.
- **port**: The local bound port.
- **localEndpoint**: IP_Endpoint variable, where the address and port of the local endpoint is copied to.

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket index was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code.

## Example

```plaintext
on start
{
  LONG  ipv4SocketHandle;
  DWORD port;
  DWORD ipv4Address[1];
  CHAR  data[255];
  CHAR  addressStr[49];

  // open a IPv4 UDP socket. This will lead to an implicit bind
  ipGetAdapterAddress(1,ipv4Address, elcount(ipv4Address));
  ipv4SocketHandle = udpOpen(ipv4Address[0], 123);
  if(ipv4SocketHandle == ~0)
  {
    writeLineEx(1, 3, "%BASE_FILE_NAME%: failed to open the socket. Error code: %d", ipGetLastError());
  }

  // get the local bound address and port
  ipGetSocketName(ipv4SocketHandle, ipv4Address[0], port);
  ipGetAddressAsString(ipv4Address[0], addressStr, elcount(addressStr));
  writeLineEx(1, 1, "%BASE_FILE_NAME%: The IPv4 socket is bound to address %s and port %d", addressStr, port);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
