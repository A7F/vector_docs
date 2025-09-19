[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionTCPSend.md)

**CAPL Functions** » **TCP/IP API** » **TcpSend**

# TcpSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TcpSend( dword socket, char buffer[], dword size); // from 1`
- `long TcpSend( dword socket, struct data[], dword size); // from 2`
- `long TcpSend( dword socket, byte buffer[], dword size); // from 3`

## Method Syntax

- `socket.Send( char buffer[], dword size); // form 1`
- `socket.Send( struct data[], dword size); // from 2`
- `socket.Send( byte buffer[], dword size); // from 3`

## Description

The function sends data on the specified socket. If the send operation does not complete immediately, the operation is performed asynchronously and the function will return `SOCKET_ERROR (-1)`.

Use [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md). If the specific error code is `WSA_IO_PENDING (997)`, this indicates an asynchronous sending.

The CAPL callback [OnTcpSend](../EventProcedures/CAPLfunctionTCPIPOnTcpSend.md) will be called on completion (successful or not), providing that it is implemented in the same CAPL program.

**Note**: If the function returns with 0, the data were able to be sent immediately (synchronously). In this case, [OnTcpSend](../EventProcedures/CAPLfunctionTCPIPOnTcpSend.md) is **NOT called up**. For this reason, you must relocate the code in **OnTcpSend** to a function or call up **OnTcpSend** explicitly.

## Parameters

- **socket**: The socket handle.
- **buffer**: The buffer containing the data to be sent.
- **data**: The struct containing the data to be sent.
- **size**: The size of the data to be sent.

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md). If the specific error code is 997, this just indicates asynchronous sending. All other results are sending errors.

## Example

```c
// ---------------------------------------------------
// send tcp data.
// ---------------------------------------------------
void sendTcpData( dword socket, char data[] )
{
  long result;
  dword size;

  size = elcount(data);
  result = TcpSend(socket, data, size);
  if (result == 0)
  {
    // sending took place immediately.
    // => OnTcpSend is NOT called.
  }
  else
  {
    if (result == -1)
    {
      result = IpGetLastSocketError(socket);
      if (result == 997)
      {
        // sending is done asynchronously.
        // => OnTcpSend is called when done sending.
      }
      else
      {
        writeLineEx( 1, 3, "   [ sendTcpData: Error sending data. (%d) ]", result);
      }
    }
    else
    {
      writeLineEx( 1, 3, "   [ sendTcpData: Error sending data. (%d) ]", result);
    }
  }
}
```

[OnTcpReceive](../EventProcedures/CAPLfunctionTCPIPOnTcpReceive.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
