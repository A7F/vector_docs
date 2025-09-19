[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionTCPGetRemoteEndpoint.md)

**CAPL Functions** » **TCP/IP API** » **TcpGetRemoteEndpoint**

# TcpGetRemoteEndpoint

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```
TcpGetRemoteEndpoint( dword socket, IP_Endpoint remoteEndpoint );
```

## Method Syntax as Constructor

```
TcpSocket::getRemoteEndpoint(IP_Endpoint remoteEndpoint );
```

## Description

The function retrieves the remote endpoint of the specified connected socket.

## Parameters

- **socket**: The socket handle.
- **remoteEndpoint**: `IP_Endpoint` which returns the IP endpoint.

## Return Values

- **0**: Success
- **Any other value**: Error

## Example

```plaintext
variables
{
  TcpSocket gListenSocket;
  TcpSocket gConnectionSocket;
  char gRxBuffer[1000];
}

on start
{
  gListenSocket = TcpSocket::Open( IP_Endpoint(0.0.0.0:40004) );

  gListenSocket.Listen();
}

OnTcpListen( TcpSocket socket, long result)
{
  if (result == 0)
  {
    gConnectionSocket = TcpSocket::Accept( gListenSocket );

    {
      IP_Endpoint localEndpoint;
      IP_Endpoint remoteEndpoint;
      char localAddrStr[100];
      char remoteAddrStr[100];

      gConnectionSocket.GetSocketName( localEndpoint );
      gConnectionSocket.GetRemoteEndpoint( remoteEndpoint );

      localEndpoint.PrintEndpointToString( localAddrStr );
      remoteEndpoint.PrintEndpointToString( remoteAddrStr );
      write( "Accepted local %s, remote %s", localAddrStr, remoteAddrStr );
    }

    gConnectionSocket.Receive( gRxBuffer, elcount( gRxBuffer) );
  }
}

OnTcpReceive( TcpSocket socket, long result, IP_Endpoint remoteEndpoint, char buffer[], dword size )
{
  if (result == 0)
  {
    write( "Received: %s", buffer );

    gConnectionSocket.Send( "Response", 8 );

    gConnectionSocket.Receive( gRxBuffer, elcount( gRxBuffer) );
  }
}
```

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
