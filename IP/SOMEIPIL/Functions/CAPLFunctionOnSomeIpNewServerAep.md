[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLFunctionOnSomeIpNewServerAep.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **OnSomeIpNewServerAep**

# OnSomeIpNewServerAep

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```c
void OnSomeIpNewServerAep(dword aepHandle, IP_Endpoint localIPEndpoint);
```

## Description

This callback gets called when a server-side SOME/IP Application Endpoint gets opened.

**Note**: In case of UDP, the callback gets called for both, server and client Application Endpoints. The information provided by the **localIPEndpoint** parameter such as IP address and port number may be used to differentiate Application Endpoints.

## Parameters

- **aepHandle**: Handle of the local Application Endpoint that may e.g. be (D)TLS secured, see [SomeIpTlsAuthenticateAsClientWithConfiguration](CAPLFunctionSomeIpTlsAuthenticateAsClientWithConfiguration.md) and [SomeIpTlsAuthenticateAsServerWithConfiguration](CAPLFunctionSomeIpTlsAuthenticateAsServerWithConfiguration.md).
- **localIPEndpoint**: [IP_Endpoint](../../Objects/CAPLfunctionIPEndpoint.md) that contains the address/port of the local endpoint.

## Return Values

—

## Example

```c
void OnSomeIpNewServerAep(dword aepHandle, ip_Endpoint localIPEndpoint)
{
  if(localIPEndpoint.PortNumber == 30500)
  {
    SomeIpTlsAuthenticateAsServer(aepHandle, "Server1", 0);
  }
}
```

[SomeIpTlsAuthenticateAsClientWithConfiguration](CAPLFunctionSomeIpTlsAuthenticateAsClientWithConfiguration.md) • [SomeIpTlsAuthenticateAsServerWithConfiguration](CAPLFunctionSomeIpTlsAuthenticateAsServerWithConfiguration.md) • [OnSomeIpClientAepConnected](CAPLFunctionOnSomeIpClientAepConnected.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
