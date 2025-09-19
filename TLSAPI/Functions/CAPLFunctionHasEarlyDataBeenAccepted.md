[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/Functions/CAPLFunctionHasEarlyDataBeenAccepted.md)

[CAPL Functions](../../CAPLfunctions.md) » [TLS API](../CAPLfunctionsTLSOverview.md) » HasEarlyDataBeenAccepted

# HasEarlyDataBeenAccepted

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long HasEarlyDataBeenAccepted(dword socket)
```

## Description

To check if the early data has been accepted by the TLS 1.3 server, this function should be called, but only after a successful TLS handshake. In case the TLS 1.3 server has rejected the early data, the TLS 1.3 client can send the data again, encrypted with the application traffic keys.

## Parameters

- **socket**: The socket handle.

## Return Values

- **0**: The early data was not received or refused by the server.
- **1**: The early data was received by the server.

## Example

```plaintext
void OnTlsHandshakeComplete(dword socket, int result)
{
  if (result == 0)
  {
    if(tlsHasEarlyDataBeenAccepted(socket) == 1)
    {
      //
      // Early data has been accepted.
      //
    }
    else
    {
      //
      // Early data has been rejected. Maybe send the data again.
      //
    }
    // ...
  }
}
```

[tlsAuthenticateAsClientWithConfigurationAndEarlyData](CAPLFunctiontlsAuthenticateAsClientWithConfigurationAndEarlyData.md) • [OnTlsEarlyDataReceived](../EventProcedures/CAPLfunctionOnTlsEarlyDataReceived.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
