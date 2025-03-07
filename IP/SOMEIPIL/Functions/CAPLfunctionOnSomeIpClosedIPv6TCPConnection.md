[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionOnSomeIpClosedIPv6TCPConnection.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » OnSomeIpClosedIPv6TCPConnection, OnSomeIpClosedIPv4TCPConnection, OnSomeIpClosedTCPConnection

# OnSomeIpClosedIPv6TCPConnection, OnSomeIpClosedIPv4TCPConnection, OnSomeIpClosedTCPConnection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void OnSomeIpClosedIPv6TCPConnection(byte localIPv6Address[], dword localPort, byte remoteIPv6Address[], dword remotePort); // form 1`
- `void OnSomeIpClosedIPv4TCPConnection(dword localIPv4Address, dword localPort, dword remoteIPv4Address, dword remotePort); // form 2`
- `void OnSomeIpClosedTCPConnection(IP_Endpoint localIPEndpoint, IP_Endpoint remoteIPEndpoint); // form 3`

## Description

This callback will be called after a IL’s TCP connection has been closed.

## Parameters

- **localIPv6Address**: Local IPv6 address.
- **remoteIPv6Address**: Remote IPv6 address.
- **localIPv4Address**: Local IPv4 address.
- **remoteIPv4Address**: Remote IPv4 address.
- **localPort**: Local TCP port number.
- **remotePort**: Remote TCP port number.
- **localIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the local endpoint.
- **remoteIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the remote endpoint.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../AUTOSARethIL/CAPLfunctionsAREthILErrorCodes.md)

## Example

```c
void OnSomeIpClosedTCPConnection(IP_Endpoint localIPEndpoint, IP_Endpoint remoteIPEndpoint)
{
  char localEndpointStr[128], remoteEndpointStr[128];

  localIPEndpoint.PrintEndpointToString(localEndpointStr);
  remoteIPEndpoint.PrintEndpointToString(remoteEndpointStr);

  write("Closed connection: %s <-> %s", localEndpointStr, remoteEndpointStr);
}
```

[See Also](javascript:void(0);)