[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/Functions/CAPLfunctiontlsOpen.md)

[CAPL Functions](../../CAPLfunctions.md) » [TLS API](../CAPLfunctionsTLSOverview.md) » tlsOpen

# tlsOpen

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword tlsOpen(dword socket);
```

## Description

Opens a **TLS** socket. An existing socket handle is used to create a new **TLS** connection.

## Parameters

- **socket**: The socket handle.

## Return Values

- **INVALID_SOCKET (~0)**: The function failed. Call [tlsGetLastError](CAPLfunctiontlsGetLastError.md) to get a more specific error code.
- **Any other value**: A valid socket handle identifying the created socket.

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)