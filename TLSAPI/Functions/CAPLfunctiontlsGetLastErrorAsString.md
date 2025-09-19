[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/Functions/CAPLfunctiontlsGetLastErrorAsString.md)

# tlsGetLastErrorAsString

[CAPL Functions](../../CAPLfunctions.md) » [TLS API](../CAPLfunctionsTLSOverview.md) » tlsGetLastErrorAsString

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long tlsGetLastErrorAsString(dword socket, char buffer[], dword bufferLength );
```

## Description

Retrieves the error message of the last operation that failed on a specified socket.

## Parameters

- **socket**: The socket handle.
- **buffer**: The buffer used to store the error message.
- **bufferLength**: The size of the text buffer.

## Return Values

- **0**: The error message was written into the text buffer. In case of an invalid error code, the error message has the format "Unknown error: x" assuming the last error code x for the specified socket.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.

## Example

```plaintext
tlsOpen(clientHandle);
tlsAuthenticateAsServer(clientHandle, "Server1");

if ((tlsGetLastError(clientHandle) != 0) &&
    (tlsGetLastError(clientHandle) != 997))
{
    // an error occurred
    tlsGetLastErrorAsString(clientHandle, errorText, elcount(errorText));
    write( "tlsAuthenticateAsServer failed, %s (Result %d)", errorText, tlsGetLastError(clientHandle) );
    return;
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
