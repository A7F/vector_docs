[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthEstablishedTLSConnection.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » OnAREthEstablishedTLSConnection

# OnAREthEstablishedTLSConnection

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnAREthEstablishedTLSConnection(IP_Endpoint locaIPEndpoint, IP_Endpoint remoteIPEndpoint);
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
void OnAREthClientAepConnected(dword aepHandle, ip_Endpoint localIPEndpoint, ip_Endpoint remoteIPEndpoint)
{
  handle = aepHandle;
  AREthTlsAuthenticateAsClient(aepHandle, "Server1");
}

void OnAREthEstablishedTLSConnection(ip_Endpoint localIPEndpoint, ip_Endpoint remoteIPEndpoint)
{
  write("AREth (D)TLS established tls connection");
}
void OnAREthClosedTLSConnection(ip_Endpoint localIPEndpoint, ip_Endpoint remoteIPEndpoint, long closedByPeer)
{
  write("AREth (D)TLS closed tls connection by peer %d", closedByPeer);
}

on key 'c'
{
  long result;
  result = AREthCloseLocalApplicationEndpoint(handle);
  write("close established tcp connection result = %d", result);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)