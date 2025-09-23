# TCPGetRemoteAddressAsString

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » TCPGetRemoteAddressAsString

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TcpGetRemoteAddressAsString(dword socket, char buffer[], dword size);
```

## Description

This function retrieves the remote address of the specified connected socket in Internet standard dotted-decimal format.

## Parameters

- **socket**: The socket handle.
- **buffer**: The buffer used to store the converted address.
- **size**: The size of the address buffer.

## Return Values

- **0**: The function completed successfully.
- **1**: The provided buffer is too small.
- **2**: Anything else failed (e.g. wrong socket parameter).

## Example

—

[TcpAccept](CAPLfunctionTCPAccept.md) • [TcpConnect](CAPLfunctionTCPConnect.md)
