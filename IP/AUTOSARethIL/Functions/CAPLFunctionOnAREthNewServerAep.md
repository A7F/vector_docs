[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLFunctionOnAREthNewServerAep.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **OnAREthNewServerAep**

# OnAREthNewServerAep

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnAREthNewServerAep(dword aepHandle, IP_Endpoint localIPEndpoint);
```

## Description

This callback gets called when a server-side SOME/IP Application Endpoint gets opened.

**Note**: In case of UDP, the callback gets called for both, server and client Application Endpoints. The information provided by the **localIPEndpoint** parameter such as IP address and port number may be used to differentiate Application Endpoints.

## Parameters

- **aepHandle**: Handle of the local Application Endpoint that may e.g. be (D)TLS secured, see [AREthTlsAuthenticateAsClientWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsClientWithConfiguration.md) and [AREthTlsAuthenticateAsServerWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsServerWithConfiguration.md).
- **localIPEndpoint**: [IP_Endpoint](../../Objects/CAPLfunctionIPEndpoint.md) that contains the address/port of the local endpoint.

## Return Values

—

## Example

```plaintext
void OnAREthNewServerAep(dword aepHandle, ip_Endpoint localIPEndpoint)
{
  if(localIPEndpoint.PortNumber == 30500)
  {
    AREthTlsAuthenticateAsServer(aepHandle, "Server1", 0);
  }
}
```

[AREthTlsAuthenticateAsClientWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsClientWithConfiguration.md) • [AREthTlsAuthenticateAsServerWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsServerWithConfiguration.md) • [OnAREthClientAepConnected](CAPLFunctionOnAREthClientAepConnected.md)
