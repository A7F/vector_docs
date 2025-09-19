[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthPreConfigureTlsConnection.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthPreConfigureTlsConnection

# AREthPreConfigureTlsConnection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function needs to be called in [on start](../../../Other/CAPLfunctionsEventProceduresOverview.md).

## Function Syntax

```
AREthPreConfigureTlsConnection(ip_Endpoint localEndpoint, ip_Endpoint remoteEndpoint, char tlsConfiguration [], dword isServer);
```

## Description

Preconfigures a connection between two AEPs as a (D)TLS connection. As a difference to [AREthTlsAuthenticateAsServerWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsServerWithConfiguration.md) and [AREthTlsAuthenticateAsClientWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsClientWithConfiguration.md), different TLS configurations for different remotes can be used on the same AEP. Furthermore, it is possible to have some connections unsecured.

The (D)TLS connection needs to be defined in both nodes, the client and the server node, independently. Works in combination with [AREthTlsAuthenticateAsServerWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsServerWithConfiguration.md) and [AREthTlsAuthenticateAsClientWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsClientWithConfiguration.md) where the existing functions configure the general behavior for an entire AEP. This function can override the general behavior declared in the other functions.

## Parameters

- **localAEP**: The local application endpoint.
- **remoteAEP**: The remote application Endpoint.
- **tlsConfiguration**: The name of the TLS configuration (not the certificate name).
- **isServer**: Marks whether the given local endpoint is (D)TLS server or client.

## Return Values

- **0**: Success
- **!=0**: Error

## Example

```plaintext
on start
{
  ip_Endpoint UDP:192.168.0.1:50001 remoteEndpoint;
  ip_Endpoint UDP:192.168.0.2:50001 localEndopint1;
  ip_Endpoint UDP:192.168.0.2:50002 localEndpoint2;

  // configures two (D)TLS connections with different endpoints with our localEndpoint as server
  AREthPreConfigureTlsConnection(localEndopint1, remoteEndpoint, "ExampleConfig1", 1);
  AREthPreConfigureTlsConnection(localEndpoint2, remoteEndpoint, "ExampleConfig2", 1);
}
```

[See Also](javascript:void(0);)
