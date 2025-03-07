[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/Functions/CAPLFunctiontlsAuthenticateAsClientWithConfigurationAndEarlyData.md)

**CAPL Functions** » **TLS API** » **tlsAuthenticateAsClientWithConfigurationAndEarlyData**

# tlsAuthenticateAsClientWithConfigurationAndEarlyData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`tlsAuthenticateAsClientWithConfigurationAndEarlyData(dword socket, char configuration[], char buffer[], dword size)`

## Description

TLS 1.3 allows clients to send encrypted data to the server right after the ClientHello message on the first flight (early data) with the performance-enhancing feature zero round trip time resumption (0-RTT). Early data is only processed by the server if a Pre-Shared Key (PSK) is configured for both, TLS 1.3 client and TLS 1.3 server, and a Max Early Data Size is set > 0 in the TLS 1.3 server configuration.

## Parameters

- **socket**: The socket handle.
- **configuration**: Name of the TLS 1.3 Client configuration.
- **Buffer**: The buffer, containing the early data to be sent.
- **size**: The size of the early data to be sent.

## Return Values

- **0**: The function was successfully executed.
- **> 0**: [Error code](../../IP/AUTOSARethIL/CAPLfunctionsAREthILErrorCodes.md)

## Example

```c
void OnTcpConnect(dword socket, long result)
{
  if (result == 0)
  {
    const dword size = 19;
    CHAR earlyData[size]  = "This is early data";

    socket = tlsOpen(socket);
    tlsAuthenticateAsClientWithConfigurationAndEarlyData(socket, "TLS1.3 PSK Configuration", earlyData, size);
    if ((tlsGetLastError(socket) != 0) &&
        (tlsGetLastError(socket) != 997))
    {
      // an error occurred
      return;
    }
  }
}
```

[OnTlsEarlyDataReceived](../EventProcedures/CAPLfunctionOnTlsEarlyDataReceived.md) • [HasEarlyDataBeenAccepted](CAPLFunctionHasEarlyDataBeenAccepted.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)