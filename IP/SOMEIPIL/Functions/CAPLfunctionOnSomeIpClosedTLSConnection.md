[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionOnSomeIpClosedTLSConnection.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » OnSomeIpClosedTLSConnection

# OnSomeIpClosedTLSConnection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnSomeIpClosedTLSConnection(IP_Endpoint locaIPEndpoint, IP_Endpoint remoteIPEndpoint, long closedByPeer);
```

## Description

This callback will be called after a (D)TLS connection between the local endpoint and remote endpoint has been closed and it indicates whether the connection was closed by peer.

## Parameters

- **localIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the local endpoint.
- **remoteIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the remote endpoint.
- **closedByPeer**: Boolean value indicates whether the connection was closed by peer.

## Return Values

—

## Example

```plaintext
variables
{
  word handle;
}

void OnSomeIPClientAepConnected(dword aepHandle, ip_Endpoint localIPEndpoint, ip_Endpoint remoteIPEndpoint)
{
  handle = aepHandle;
  SomeIPTlsAuthenticateAsClient(aepHandle, "Server1");
}

void OnSomeIPEstablishedTLSConnection(ip_Endpoint localIPEndpoint, ip_Endpoint remoteIPEndpoint)
{
  write("AREth (D)TLS established tls connection");
}

void OnSomeIPClosedTLSConnection(ip_Endpoint localIPEndpoint, ip_Endpoint remoteIPEndpoint, long closedByPeer)
{
  write("AREth (D)TLS closed tls connection by peer %d", closedByPeer);
}

on key 'c'
{
  long result;
  result = SomeIPCloseLocalApplicationEndpoint(handle);
  write("close established tcp connection result = %d", result);
}
```

[See Also](javascript:void(0);)
