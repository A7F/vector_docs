[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetLastSocketErrorAsString.md)

**CAPL Functions** » **TCP/IP API** » **IpGetLastSocketErrorAsString**

# IpGetLastSocketErrorAsString

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetLastSocketErrorAsString( dword socket, char text[], dword count);
```

## Method Syntax

```plaintext
socket.GetLastSocketErrorAsString( char text[], dword count);
```

## Description

The function retrieves the error message of the last operation that failed on the specified socket (see [Winsock 2 error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md)).

## Parameters

- **socket**: The socket handle.
- **text**: The buffer used to store the error message.
- **count**: The size of the text buffer.

## Return Values

- **0**: The error message was written into the text buffer. In case of an invalid error code, the error message has the format "Unknown error: x" assuming the last error code x for the specified socket.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.

## Example

```plaintext
on start
{
  const dword INVALID_SOCKET = ~0; // invalid socket constant
  dword socket = INVALID_SOCKET;   // a socket
  char errMsg[255];                // error message buffer.

  // just create an unspecified socket.
  socket = UdpOpen( 0, 1 );

  // produce an error e.g. using invalid parameters to UdpSendTo
  if (UdpSendTo(socket, 0, 0, "a", 1) == -1)
  {
    IpGetLastSocketErrorAsString( socket, errMsg, elcount(errMsg) );
    writeLineEx(1, 3, "IpGetLastSocketErrorAsString: %s", errMsg);
  }

  // close the socket.
  UdpClose(socket);
}
```

[IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) • [IpGetLastError](CAPLfunctionIPGetLastError.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)