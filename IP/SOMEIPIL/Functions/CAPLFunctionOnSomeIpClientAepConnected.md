[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLFunctionOnSomeIpClientAepConnected.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **OnSomeIpClientAepConnected**

# OnSomeIpClientAepConnected

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnSomeIpClientAepConnected(dword aepHandle, IP_Endpoint localIPEndpoint, IP_Endpoint remoteIPEndpoint);
```

## Description

This callback gets called when a client-side SOME/IP Application Endpoint gets connected to a remote peer.

## Parameters

- **aepHandle**: Handle of the local Application Endpoint that may e.g. be (D)TLS secured, see [SomeIpTlsAuthenticateAsClientWithConfiguration](CAPLFunctionSomeIpTlsAuthenticateAsClientWithConfiguration.md) and [SomeIpTlsAuthenticateAsServerWithConfiguration](CAPLFunctionSomeIpTlsAuthenticateAsServerWithConfiguration.md).

- **localIPEndpoint**: [IP_Endpoint](../../Objects/CAPLfunctionIPEndpoint.md) that contains the address/port of the local endpoint.

- **remoteIPEndpoint**: [IP_Endpoint](../../Objects/CAPLfunctionIPEndpoint.md) that contains the address/port of the remote endpoint.

## Return Values

—

## Example

```plaintext
void OnSomeIpClientAepConnected(dword aepHandle, ip_Endpoint localIPEndpoint, ip_Endpoint remoteIPEndpoint)
{
  if(remoteIPEndpoint.PortNumber == 30500)
  {
    SomeIpAuthenticateAsClient(aepHandle, "Server1");
  }
}
```

[SomeIpTlsAuthenticateAsClientWithConfiguration](CAPLFunctionSomeIpTlsAuthenticateAsClientWithConfiguration.md) • [SomeIpTlsAuthenticateAsServerWithConfiguration](CAPLFunctionSomeIpTlsAuthenticateAsServerWithConfiguration.md) • [OnSomeIpNewServerAep](CAPLFunctionOnSomeIpNewServerAep.md)
