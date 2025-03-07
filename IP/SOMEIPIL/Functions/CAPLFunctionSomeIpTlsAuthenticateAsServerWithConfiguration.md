[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLFunctionSomeIpTlsAuthenticateAsServerWithConfiguration.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpTlsAuthenticateAsServerWithConfiguration

# SomeIpTlsAuthenticateAsServerWithConfiguration

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

`SomeIpTlsAuthenticateAsServerWithConfiguration(dword connectionHandle, char configuration[])`

## Description

Starts the [TLS](../../../../CANoeCANalyzer/Security/SecurityTLS.md) authentication handshake as server. Certificate common names and Pre Shared Key names have to match the entries in the Vector Security Manager TLS configuration. It is possible to copy the TLS configuration name from the security profile.

## Parameters

- **connectionHandle**: Handle of the TLS socket to be used.
- **configuration**: Name of the TLS configuration.

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../../AUTOSARethIL/CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
dword res;
dword connection;

if (socket == gServerSocket1)
{
    connection = tcpAccept(socket);
    connection = TlsOpen(connection);
    write("%FILE_NAME_NO_EXT%: Server %d connection %d", socket, connection);
    res = tlsAuthenticateAsServerWithConfiguration(connection, "PSK K1");
}
```

[SomeIpTlsAuthenticateAsClientWithConfiguration](CAPLFunctionSomeIpTlsAuthenticateAsClientWithConfiguration.md) • [OnSomeIpNewServerAep](CAPLFunctionOnSomeIpNewServerAep.md) • [OnSomeIpClientAepConnected](CAPLFunctionOnSomeIpClientAepConnected.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)