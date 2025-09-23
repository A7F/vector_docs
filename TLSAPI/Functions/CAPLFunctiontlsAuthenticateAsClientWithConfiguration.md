[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/Functions/CAPLFunctiontlsAuthenticateAsClientWithConfiguration.md)

[CAPL Functions](../../CAPLfunctions.md) » [TLS API](../CAPLfunctionsTLSOverview.md) » tlsAuthenticateAsClientWithConfiguration

# tlsAuthenticateAsClientWithConfiguration

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

`tlsAuthenticateAsClientWithConfiguration(dword connectionHandle,char configuration[])`

## Description

Starts the [TLS](../../../CANoeCANalyzer/Security/SecurityTLS.md) authentication handshake as client. Certificate common names and Pre Shared Key names have to match the entries in the Vector Security Manager TLS configuration. It is possible to copy the TLS configuration name from the security profile.

## Parameters

- **connectionHandle**: Handle of the TLS socket to be used.
- **configuration**: Name of the TLS configuration.

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../../IP/AUTOSARethIL/CAPLfunctionsAREthILErrorCodes.md)

## Example

```c
void OnTcpConnect( dword socket, long result)
{
  if (result == 0)
  {
    socket = tlsOpen(socket);
    tlsAuthenticateAsClientWithConfiguration(socket, "PSK K1");
    if ((tlsGetLastError(socket) != 0) &&
        (tlsGetLastError(socket) != 997))
    {
      // an error occurred
      return;
    }
  }
}
```

[tlsAuthenticateAsServerWithConfiguration](CAPLFunctiontlsAuthenticateAsServerWithConfiguration.md)
