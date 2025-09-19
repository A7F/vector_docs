[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionUDPOpen.md)

**CAPL Functions** » **TCP/IP API** » **UdpOpen**

# UdpOpen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword UdpOpen( dword ipv4Address, dword port); // form 1`
- `dword UdpOpen( byte ipv6Address[], dword port); // form 2`
- `dword UdpOpen( IP_Endpoint localEndpoint); // form 3`

## Method Syntax

- `UdpSocket::Open( dword ipv4Address, dword port); // form 1`
- `UdpSocket::Open( byte ipv6Address[], dword port); // form 2`
- `UdpSocket::Open( IP_Endpoint localEndpoint ); // form 3`

## Description

Depending on the address type, the function creates either an IPv4 or IPv6 UDP socket for use in connectionless, datagram-oriented communications. All parameters may be zero. If the port parameter is non-zero, the socket is implicitly bound to the given port. Otherwise, the socket can be bound later on with [IpBind](CAPLfunctionIPBind.md) or it will be automatically bound to a free port with [UdpSendTo](CAPLfunctionUDPSendTo.md).

**Note:** If an address is given but the port is zero, **no** implicit bind is performed. Please use [IpBind](CAPLfunctionIPBind.md) after opening the socket in this case.

## Parameters

- **ipv4Address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) local IPv4 address to be used with the socket. If set to 0, then the socket is address unspecific (address wildcard). It then can be used for all adapters on any address.

- **ipv6Address**: The local IPv6 address in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md). Like in the IPv4 address, an address wildcard can be retrieved using [IpGetAddressAsArray](CAPLfunctionIPGetAddressAsArray.md)("::", ipv6AddrArray).

- **port**: The port in host-byte order to be used with the socket. If set to 0, then the socket is port unspecific (port wildcard).

- **localEndpoint**: Binds the socket to this local endpoint. IP Address can be 0, if the socket should not be bound to an address. Port number can be undefined, if a dynamic port number should be used.

  **Examples:**
  - `IP_Endpoint(192.168.1.1:4000)` – Bind to address and port
  - `IP_Endpoint(0.0.0.0:4000)` – Bind only to port for IPv4
  - `IP_Endpoint([::]:4000)` – Bind only to port for IPv6
  - `IP_Endpoint(192.168.1.1)` – Bind to address and choose a dynamic port

## Return Values

- **INVALID_SOCKET (~0)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

- **Any other value**: A valid socket handle identifying the created socket.

## Example

```plaintext
variables
{
  UdpSocket gSocket;
  char      gRxBuffer[1000];
}

on start
{
  gSocket = UdpSocket::Open( IP_Endpoint(0.0.0.0:40001) );
  gSocket.SendTo( IP_Endpoint(192.168.0.2:40002), "Hello", 5 );
  gSocket.ReceiveFrom( gRxBuffer, elcount( gRxBuffer) );
}

OnUdpReceiveFrom( UdpSocket socket, long result, IP_Endpoint remoteEndpoint, char buffer[], dword size)
{
  if (result == 0)
  {
    write( "Received: %s", buffer );
    gSocket.ReceiveFrom( gRxBuffer, elcount( gRxBuffer) );
  }
}
```

[UdpClose](CAPLfunctionUDPClose.md) • [Create UDP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
