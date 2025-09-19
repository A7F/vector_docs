# OnTcpReceive

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnTcpReceive.md)

**CAPL Functions** » **TCP/IP API** » OnTcpReceive

## Function Syntax

- `void OnTcpReceive( dword socket, long result, dword address, dword port, char buffer[], dword size); // form 1`
- `void OnTcpReceive( dword socket, long result, dword address, dword port, byte buffer[], dword size); // form 2`
- `void OnTcpReceive( dword socket, long result, byte ipv6Address[], dword port, char buffer[], dword size); // form 3`
- `void OnTcpReceive( dword socket, long result, byte ipv6Address[], dword port, byte buffer[], dword size); // form 4`
- `void OnTcpReceive( dword socket, long result, IP_Endpoint remoteEndpoint, char buffer[], dword size); // form 5`
- `void OnTcpReceive( dword socket, long result, IP_Endpoint remoteEndpoint, byte buffer[], dword size); // form 6`

## Method Syntax

- `void OnTcpReceive( TcpSocket socket, long result, dword address, dword port, char buffer[], dword size); // form 1`
- `void OnTcpReceive( TcpSocket socket, long result, dword address, dword port, byte buffer[], dword size); // form 2`
- `void OnTcpReceive( TcpSocket socket, long result, byte ipv6Address[], dword port, char buffer[], dword size); // form 3`
- `void OnTcpReceive( TcpSocket socket, long result, byte ipv6Address[], dword port, byte buffer[], dword size); // form 4`
- `void OnTcpReceive( TcpSocket socket, long result, IP_Endpoint remoteEndpoint, char buffer[], dword size); // form 5`
- `void OnTcpReceive( TcpSocket socket, long result, IP_Endpoint remoteEndpoint, byte buffer[], dword size); // form 6`

## Description

If the CAPL program implements this callback it is called when a receive operation on a TCP socket completes.

The stack contains a data queue that is reduced by [TcpReceive](../Functions/CAPLfunctionTCPReceive.md) as soon as data are located there.

So that additional data from the data queue will be received in the future for the socket, [TcpReceive](../Functions/CAPLfunctionTCPReceive.md) must be called up again within the callback.

**Note:** If **result** = 0 and **size** = 0, socket was closed by the communication peer, see example.

## Parameters

- **socket**: The socket handle or socket object.
- **result**: The specific result code of the operation. If the operation completed successfully the value is zero. Otherwise the value is an [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md). If **result** = 0 and **size** = 0, socket was closed by the communication peer, see example.
- **address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) remote IPv4 address of the location which sent the data.
- **ipv6Address**: The remote IPv6 address in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **port**: The remote port of the location which sent the data in host-byte order.
- **buffer**: The buffer into which the data was stored.
- **size**: The size of the received data. If **result** = 0 and **size** = 0, socket was closed by the communication peer, see example.
- **remoteEndpoint**: The remote endpoint of the location which sent the data.

## Return Values

—

## Example

```plaintext
variables
{
  const dword INVALID_SOCKET =  0;
  const dword SOCKET_ERROR   = -1;
  const long  WSA_IO_PENDING =  997;

  dword gSocket;  // socket handle
}

void foo()
{
  int rc = 0;
  char buffer[65*1024];

  rc = TcpReceive(gSocket, buffer, elcount(buffer));
  if (rc==0)
  {
    // The receive operation does complete immediately, so the callback
    // function OnTcpReceive was already called.
  }
  else if (rc==SOCKET_ERROR)
  {
    long ipLastErr;
    ipLastErr = IpGetLastSocketError(gSocket);
    if (ipLastErr==WSA_IO_PENDING)
    {
      // The receive operation is performed asynchronously
    }
    else
    {
      Write("TcpReceive: operation failed (IpGetLastSocketError=%d)", ipLastErr);
      TCPClose(gSocket);
      gSocket = INVALID_SOCKET;
    }
  }
  else
  {
    Write("TcpReceive: operation failed (%d)", rc);
    TCPClose(gSocket);
    gSocket = INVALID_SOCKET;
  }
}

void OnTcpReceive( dword socket, long result, dword address, dword port, char buffer[], dword size)
{
  if (result==0)
  {
    if (size==0)
    {
      // Size of zero indicates that the socket was closed by the communication peer.
      Write("OnTcpReceive: socket closed by peer");
      TCPClose(gSocket);
      gSocket = INVALID_SOCKET;
    }
    else
    {
      // Sucessfully received some bytes over the TCP/IP connection.
      // Do something useful with the data ...
      // ... and continue receiving ...
      foo ();
    }
  }
  else
  {
    long ipLastErr;
    ipLastErr = IpGetLastSocketError(gSocket);
    Write("OnTcpReceive: operation failed (result=%d IpGetLastSocketError=%d)", result, ipLastErr);
    TCPClose(gSocket);
    gSocket = INVALID_SOCKET;
  }
}
```

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
