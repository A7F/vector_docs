[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpGetSocketAddressFamily.md)

**CAPL Functions** » **TCP/IP API** » **IpGetSocketAddressFamily**

# IpGetSocketAddressFamily

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetSocketAddressFamily(dword socket);
```

## Description

The function returns the address family of the given socket.

## Parameters

- **socket**: The socket handle.

## Return Values

- **AF_INET (2)**: The socket belongs to the IPv4 address family.
- **AF_INET6 (28)**: The socket belongs to the IPv6 address family.
- **SOCKET_ERROR (-1)**: Invalid socket handle.

## Example

```plaintext
on start
{
  const dword INVALID_SOCKET = ~0; // invalid socket constant
  dword socket = INVALID_SOCKET;   // a socket
  char errMsg[255];               // error message buffer.
  byte ipv6Addr[16];
  dword port = 12345;
  long result;                    // function result

  // just create a socket.
  socket = UdpOpen(0, port);
  result = IpGetSocketAddressFamily(socket);
  if (result != -1)
  {
    writeLineEx(1, 3, "IpGetSocketAddressFamily returned %d.", result);
  }
  else
  {
    writeLineEx(1, 3, "IpGetSocketAddressFamily: Invalid socket handle.");
  }

  // close the socket.
  UdpClose(socket);

  // ... and for IPv6 ...
  IpGetAddressAsArray("::", ipv6Addr); // get an IPv6 "zero" address
  socket = UdpOpen(ipv6Addr, 0);
  result = IpGetSocketAddressFamily(socket);
  if (result != -1)
  {
    writeLineEx(1, 3, "IpGetSocketAddressFamily returned %d.", result);
  }
  else
  {
    writeLineEx(1, 3, "IpGetSocketAddressFamily: Invalid socket handle.");
  }
  // close the socket.
  UdpClose(socket);
}
```

[IpGetAdapterAddressCount](CAPLfunctionIpGetAdapterAddressCount.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
