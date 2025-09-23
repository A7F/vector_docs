[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLFunctionAREthTlsAuthenticateAsClientWithConfiguration.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthTlsAuthenticateAsClientWithConfiguration

# AREthTlsAuthenticateAsClientWithConfiguration

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`AREthTlsAuthenticateAsClientWithConfiguration(dword connectionHandle, char configuration[])`

## Description

Starts the [TLS](../../../../CANoeCANalyzer/Security/SecurityTLS.md) authentication handshake as client. Certificate common names and Pre Shared Key names have to match the entries in the Vector Security Manager TLS configuration. It is possible to copy the TLS configuration name from the security profile.

## Parameters

- **connectionHandle**: Handle of the TLS socket to be used.
- **configuration**: Name of the TLS configuration.

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

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

[AREthTlsAuthenticateAsServerWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsServerWithConfiguration.md) • [OnAREthNewServerAep](CAPLFunctionOnAREthNewServerAep.md) • [OnAREthClientAepConnected](CAPLFunctionOnAREthClientAepConnected.md)
