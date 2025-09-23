[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionUDPSendTo.md)

**CAPL Functions** » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » UdpSendTo

# UdpSendTo

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long UdpSendTo( dword socket, dword address, dword port, char buffer[], dword size); // form 1`
- `long UdpSendTo( dword socket, byte ipv6Address[], dword port, char buffer[], dword size); // form 2`
- `long UdpSendTo( dword socket, dword address, dword port, struct data[], dword size); // form 3`
- `long UdpSendTo( dword socket, dword address, dword port, byte buffer[], dword size); // form 4`
- `long UdpSendTo( dword socket, byte ipv6Address[], dword port, struct data[], dword size); // form 5`
- `long UdpSendTo( dword socket, byte ipv6Address[], dword port, byte buffer[], dword size); // form 6`
- `long UdpSendTo( dword socket, IP_Endpoint remoteEndpoint, char buffer[], dword size); // form 7`
- `long UdpSendTo( dword socket, IP_Endpoint remoteEndpoint, byte buffer[], dword size); // form 8`
- `long UdpSendTo( dword socket, IP_Endpoint remoteEndpoint, struct data[], dword size); // form 9`

## Method Syntax

- `socket.SendTo( dword address, dword port, char buffer[], dword size); // form 1`
- `socket.SendTo( byte ipv6Address[], dword port, char buffer[], dword size); // form 2`
- `socket.SendTo( dword address, dword port, struct data[], dword size); // form 3`
- `socket.SendTo( dword address, dword port, byte buffer[], dword size); // form 4`
- `socket.SendTo( byte ipv6Address[], dword port, struct data[], dword size); // form 5`
- `socket.SendTo( byte ipv6Address[], dword port, byte buffer[], dword size); // form 6`
- `socket.SendTo( IP_Endpoint remoteEndpoint, char buffer[], dword size); // form 7`
- `socket.SendTo( IP_Endpoint remoteEndpoint, byte buffer[], dword size); // form 8`
- `socket.SendTo( IP_Endpoint remoteEndpoint, struct data[], dword size); // form 9`

## Description

The function sends data to the specified location. If the send operation does not complete immediately, the operation is performed asynchronously and the function will return `SOCKET_ERROR (-1)`. Use [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code. If the specific error code is `WSA_IO_PENDING (997)`, the CAPL callback [OnUdpSendTo](../EventProcedures/CAPLfunctionTCPIPOnUdpSendTo.md) will be called on completion (successful or not), providing that it is implemented in the same CAPL program.

If the operation has been processed synchronously, the CAPL callback [OnUdpSendTo](../EventProcedures/CAPLfunctionTCPIPOnUdpSendTo.md) is not called up (see also [TcpSend](CAPLfunctionTCPSend.md)).

## Parameters

- **socket**: The socket handle.
- **address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 address of the destination in [network-byte order](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **ipv6Address**: The destination IPv6 address in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **port**: The port of the destination in host-byte order.
- **buffer**: The buffer containing the data to be sent.
- **data**: The struct containing the data to be sent.
- **size**: The size of the data to be sent.
- **remoteEndpoint**: The destination endpoint. IP address and port number must be specified.
  - Example:
    - `IP_Endpoint( 192.168.1.1:40001 )`
    - `IP_Endpoint( [FC00::0001]:40001 )`

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md). If the specific error code is 997, this just indicates asynchronous sending. All other results are sending errors.

## Example

```plaintext
variables
{
  UdpSocket gSocket;
  char gRxBuffer[1000];
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

[UdpOpen](CAPLfunctionUDPOpen.md) • [UdpClose](CAPLfunctionUDPClose.md) • [UdpReceiveFrom](CAPLfunctionUDPReceiveFrom.md) • [OnUdpSendTo](../EventProcedures/CAPLfunctionTCPIPOnUdpSendTo.md)
