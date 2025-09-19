[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionTCPReceive.md)

## TcpReceive

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » TcpReceive

### Function Syntax

- `long TcpReceive( dword socket, char buffer[], dword size); // form 1`
- `long TcpReceive( dword socket ); // form 2`
- `long TcpReceive( dword socket, dword bytesToReceive ); // form 3`
- `long TcpReceive( dword socket, dword bytesToReceive, char buffer[] ); // form 4`
- `long TcpReceive( dword socket, dword bytesToReceive, dword offset, char buffer[] ); // form 5`
- `long TcpReceive( dword socket, dword bytesToReceive, byte buffer[] ); // form 6`
- `long TcpReceive( dword socket, dword bytesToReceive, dword offset, byte buffer[] ); // form 7`

### Method Syntax

- `socket.Receive( char buffer[], dword size); // form 1`
- `socket.Receive( ); // form 2`
- `socket.Receive( dword bytesToReceive ); // form 3`
- `socket.Receive( dword bytesToReceive, char buffer[] ); // form 4`
- `socket.Receive( dword bytesToReceive, dword offset, char buffer[] ); // form 5`
- `socket.Receive( dword bytesToReceive, byte buffer[] ); // form 6`
- `socket.Receive( dword bytesToReceive, dword offset, byte buffer[] ); // form 7`

### Description

The function receives data on the given socket.

- The forms 3-7 are not available if the operating system stack is selected or TLS is used.
- If the form 2 or 3 is used, the receive buffer will be created internally. This buffer will be returned in the [OnTcpReceive](../EventProcedures/CAPLfunctionTCPIPOnTcpReceive.md) callback and is only valid in the receive callback. In the other forms a receive buffer is given by you. In this case the same buffer is returned in the callback.
- If one of the forms 3-7 is used, the callback is called only when the specified amount of data has been received.
- In the forms 5 and 7 it is possible to define an offset in the given buffer, where the received data should be written to. The whole Buffer will be returned in the callback.

The received data will be returned in the CAPL callback [OnTcpReceive](../EventProcedures/CAPLfunctionTCPIPOnTcpReceive.md) in every case.

If the receive operation does not complete immediately the operation is performed asynchronously and the function will return SOCKET_ERROR (-1).

Use [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code.

If the specific [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md) is WSA_IO_PENDING (997), this confirms an asynchronous receiving and is no receive error.

The CAPL callback [OnTcpReceive](../EventProcedures/CAPLfunctionTCPIPOnTcpReceive.md) will be called on completion (successful or not), provided it is implemented in the same CAPL program.

### Parameters

- **socket**: The socket handle.
- **buffer**: The buffer used to store the incoming data.
- **size**: The size of the data buffer.
- **bytesToReceive**: The amount of data that has to be received before the [OnTcpReceive](../EventProcedures/CAPLfunctionTCPIPOnTcpReceive.md) callback will be called. This is limited by the internal receive buffer size.
- **offset**: The offset where the received data will be written in the given buffer.

### Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed, if [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) returns an [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md) different of 997.

### Example

```c
void startReceive ( dword socket, char buffer[] )
{
  long result;
  result = TcpReceive( socket, buffer, elcount(buffer) );
  if (result == -1)
  {
    result = IpGetLastSocketError(socket);
    if (result != 997)
    {
      // failure
      writeLineEx( 1, 3, "TcpReceive error %d", result);
    }
  }
  else
  {
    // failure
    writeLIneEx( 1, 3, "TcpReceive error %d", result);
  }
}
```

You can find further examples in the Ethernet chat sample configurations [Open Folder](javascript:startCANoeLauncher('&quot;SAMPLES:\\Ethernet\\Simulation')) (only with installed Ethernet option available).

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
