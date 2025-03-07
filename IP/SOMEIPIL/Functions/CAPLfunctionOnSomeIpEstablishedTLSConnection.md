[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionOnSomeIpEstablishedTLSConnection.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **OnSomeIpEstablishedTLSConnection**

# OnSomeIpEstablishedTLSConnection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnSomeIpEstablishedTLSConnection(IP_Endpoint locaIPEndpoint, IP_Endpoint remoteIPEndpoint);
```

## Description

This callback will be called after a (D)TLS connection between the local endpoint and remote endpoint has been established.

## Parameters

- **localIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the local endpoint.
- **remoteIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the remote endpoint.

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
```markdown
- OnSomeIpEventReceived
- OnSomeIpFieldNotification
- OnSomeIpMethodError
- OnSomeIpMethodRequest
- OnSomeIpMethodResponse
- OnSomeIpPrepareEvent
- OnSomeIpClientAepConnected
- OnSomeIpClosedIPv6TCPConnection, OnSomeIpClosedIPv4TCPConnection, OnSomeIpClosedTCPConnection
- OnSomeIpClosedTLSConnection
- OnSomeIpEstablishedIPv6TCPConnection, OnSomeIpEstablishedIPv4TCPConnection, OnSomeIpEstablishedTCPConnection
- OnSomeIpEstablishedTLSConnection
- OnSomeIpMessage
- OnSomeIpNewServerAep
- OnSomeIpProcessRxMessage
- OnSomeIpProcessTxMessage
- OnSomeIpSDClientEventGroupStatusChanged
- OnSomeIpSDClientServiceStatusChanged
- OnSomeIpSDServerEventGroupStatusChanged
- SomeIpCloseEstablishedTCPConnection
- SomeIpEstablishTCPConnection
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)