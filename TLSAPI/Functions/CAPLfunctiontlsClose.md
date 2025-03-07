[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/Functions/CAPLfunctiontlsClose.md)

## CAPL Functions » TLS API » tlsClose

### Function Syntax

```plaintext
long tlsClose(dword socket, dword closeUnderlyingSocket);
```

### Description

Closes the given TLS connection. This sends a **TLS** alert message to the peer node. The underlying socket will be closed automatically if the parameter **closeUnderlyingSocket** is set to a value greater than 0.

### Parameters

- **socket**: The socket handle.
- **closeUnderlyingSocket**:
  - 0: do not close underlying socket.
  - unequal 0: close the underlying socket.

### Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](../../TCPIPAPI/Functions/CAPLfunctionIPGetLastSocketError.md) to get a more specific error code. If the specific error code is 997, this just indicates an asynchronous operation is in progress.
- **TLS_ERROR (-2)**: The function failed. Call [tlsGetLastError](CAPLfunctiontlsGetLastError.md) to get a more specific error code. If the specific error code is 997, this just indicates an asynchronous operation is in progress.

### Example

```c
void ClientStop()
{
  //
  // Close TLS socket and underlying socket
  //

  tlsClose(gTlsClientSocket, 1);
  gTlsClientSocket = 0;
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)