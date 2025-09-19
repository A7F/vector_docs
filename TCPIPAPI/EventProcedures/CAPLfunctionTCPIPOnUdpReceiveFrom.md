[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnUdpReceiveFrom.md)

**CAPL Functions** » **TCP/IP API** » **OnUdpReceiveFrom**

# OnUdpReceiveFrom

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void OnUdpReceiveFrom( dword socket, long result, dword address, dword port, char buffer[], dword size); // form 1`
- `void OnUdpReceiveFrom( dword socket, long result, dword address, dword port, byte buffer[], dword size); // form 2`
- `void OnUdpReceiveFrom( dword socket, long result, byte ipv6Address[], dword port, char buffer[], dword size); // form 3`
- `void OnUdpReceiveFrom( dword socket, long result, byte ipv6Address[], dword port, byte buffer[], dword size); // form 4`
- `void OnUdpReceiveFrom( dword socket, long result, IP_Endpoint remoteEndpoint, char buffer[], dword size); // form 5`
- `void OnUdpReceiveFrom( dword socket, long result, IP_Endpoint remoteEndpoint, byte buffer[], dword size); // form 6`

## Method Syntax

- `void OnUdpReceiveFrom( UdpSocket socket, long result, dword address, dword port, char buffer[], dword size); // form 1`
- `void OnUdpReceiveFrom( UdpSocket socket, long result, dword address, dword port, byte buffer[], dword size); // form 2`
- `void OnUdpReceiveFrom( UdpSocket socket, long result, byte ipv6Address[], dword port, char buffer[], dword size); // form 3`
- `void OnUdpReceiveFrom( UdpSocket socket, long result, byte ipv6Address[], dword port, byte buffer[], dword size); // form 4`
- `void OnUdpReceiveFrom( UdpSocket socket, long result, IP_Endpoint remoteEndpoint, char buffer[], dword size); // form 5`
- `void OnUdpReceiveFrom( UdpSocket socket, long result, IP_Endpoint remoteEndpoint, byte buffer[], dword size); // form 6`

## Description

If the CAPL program implements this callback it is called when an asynchronous receive operation on an UDP socket completes.

The stack contains a data queue that is reduced by [UdpReceiveFrom](../Functions/CAPLfunctionUDPReceiveFrom.md) as soon as data are located there.

So that additional data from the data queue will be received in the future for the socket, [UdpReceiveFrom](../Functions/CAPLfunctionUDPReceiveFrom.md) must be called up again within the callback.

## Parameters

- **socket**: The socket handle or socket object.
- **result**: The result code of the asynchronous operation. If the operation completed successfully the value is 0. Otherwise the value is an [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md).
- **address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) remote IPv4 address of the location which sent the data.
- **ipv6Address**: The remote IPv6 address in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **port**: The remote port of the location which sent the data in host-byte order.
- **buffer**: The buffer into which the data was stored.
- **size**: The number of bytes received.
- **remoteEndpoint**: The remote endpoint of the location which sent the data.

## Return Values

—

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

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
