[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLFunctionOnAREthClientAepConnected.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **OnAREthClientAepConnected**

# OnAREthClientAepConnected

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnAREthClientAepConnected(dword aepHandle, IP_Endpoint localIPEndpoint, IP_Endpoint remoteIPEndpoint);
```

## Description

This callback gets called when a client-side SOME/IP Application Endpoint gets connected to a remote peer.

## Parameters

- **aepHandle**: Handle of the local Application Endpoint that may e.g. be (D)TLS secured, see [AREthTlsAuthenticateAsClientWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsClientWithConfiguration.md) and [AREthTlsAuthenticateAsServerWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsServerWithConfiguration.md).

- **localIPEndpoint**: [IP_Endpoint](../../Objects/CAPLfunctionIPEndpoint.md) that contains the address/port of the local endpoint.

- **remoteIPEndpoint**: [IP_Endpoint](../../Objects/CAPLfunctionIPEndpoint.md) that contains the address/port of the remote endpoint.

## Return Values

—

## Example

```plaintext
void OnAREthClientAepConnected(dword aepHandle, ip_Endpoint localIPEndpoint, ip_Endpoint remoteIPEndpoint)
{
  if(remoteIPEndpoint.PortNumber == 30500)
  {
    AREthTlsAuthenticateAsClient(aepHandle, "Server1");
  }
}
```

[AREthTlsAuthenticateAsClientWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsClientWithConfiguration.md) • [AREthTlsAuthenticateAsServerWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsServerWithConfiguration.md) • [OnAREthNewServerAep](CAPLFunctionOnAREthNewServerAep.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
