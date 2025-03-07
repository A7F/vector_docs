[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionTCPOpen.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » TcpOpen

# TcpOpen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword TcpOpen( dword ipv4Address, dword port);` // form 1
- `dword TcpOpen( byte ipv6Address[], dword port);` // form 2
- `dword TcpOpen( IP_Endpoint localEndpoint );` // form 3

## Method Syntax as Constructor

- `TcpSocket::Open(IP_Endpoint localEndpoint );`

## Description

Depending on the address type, the function creates either an IPv4 or IPv6 TCP socket for use in connection-based, message-oriented communications. All parameters may be zero. If the port parameter is non-zero, the socket is implicitly bound to the given port. Otherwise, the socket can be bound later on with [IpBind](CAPLfunctionIPBind.md) or it will be automatically bound to a free port with [TcpConnect](CAPLfunctionTCPConnect.md).

**Note:** If an address is given but the port is zero **no** implicit bind is performed. Please use [IpBind](CAPLfunctionIPBind.md) after opening the socket in this case.

## Parameters

- **ipv4Address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) local IPv4 address to be used with the socket. If set to 0, then the socket is address unspecific (address wildcard).
- **ipv6Address**: The local IPv6 address in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md). Like in the IPv4 address, an address wildcard can be retrieved using [IpGetAddressAsArray](CAPLfunctionIPGetAddressAsArray.md)("::", ipv6AddrArray).
- **port**: The port in host-byte order to be used with the socket. If set to 0, then the socket is port unspecific (port wildcard).
- **localEndpoint**: Bind the socket to this local endpoint. IP Address can be 0, if the socket should not be bound to an address. Port number can be undefined, if a dynamic port number should be used. Examples:
  - `IP_Endpoint(192.168.1.1:4000)` – Bind to address and port
  - `IP_Endpoint(0.0.0.0:4000)` – Bind only to port for IPv4
  - `IP_Endpoint([::]:4000)` – Bind only to port for IPv6
  - `IP_Endpoint(192.168.1.1)` – Bind to address and choose a dynamic port

## Return Values

- **INVALID_SOCKET (~0)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.
- **Any other value**: A valid socket handle identifying the created socket.

## Example

```cpp
// ---------------------------------------------------
// start server
// ---------------------------------------------------
void serverStart()
{
  listenSocket = TcpOpen(0, listenPort);
  if (listenSocket != ~0)
  {
    if (TcpListen(listenSocket) == 0)
    {
      // success…
    }
    else
    {
      writeLineEx(1, 3, " [ TcpListen: Error listening on socket. ]");
      TcpClose(listenSocket);
      listenSocket = ~0;
    }
  }
  else
  {
    writeLineEx(1, 3, " [ TcpOpen: Error opening TCP Socket on port %d. (Error %d) ]", listenPort, IpGetLastError());
  }
}
```

You can find further examples in the Ethernet chat sample configurations [Open Folder](javascript:startCANoeLauncher('&quot;SAMPLES:\\Ethernet\\Simulation')) (only with installed Ethernet option available).

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)