[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPSetSocketOption.md)

## CAPL Functions » TCP/IP API » IpSetSocketOption

### Function Syntax

- `long IpSetSocketOption( dword socket, long level, long name, long value); // form 1`
- `long IpSetSocketOption( dword socket, char level[], char name[], long value); // form 2`

### Method Syntax

- `socket.SetSocketOption( long level, long name, long value); // form 1`
- `socket.SetSocketOption( char level[], char name[], long value); // form 2`

### Description

The function modifies a [socket option](../CAPLfunctionsTCPIPSocketOptions.md).

The function is dependent on the [selected stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md).

### Parameters

- **socket**: The socket handle.
- **level**: The level at which the option is defined, e.g. SOL_SOCKET (0xFFFF). See [Socket Options](../CAPLfunctionsTCPIPSocketOptions.md) for all supported socket levels.
- **name**: The socket option name to be modified, e.g. SO_BROADCAST (0x0020). See [Socket Options](../CAPLfunctionsTCPIPSocketOptions.md) for all supported socket options.
- **value**: The value to be set for the socket option.

### Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

### Example

```plaintext
on start
{
  CHAR errorMessage[255];
  LONG tcpSocket;
  LONG result;
  LONG value;

  // open a tcp socket
  tcpSocket = tcpOpen(0,0);
  if( tcpSocket == ~0 )
  {
    write("open tcp socket failed. Last error was %d", ipGetLastError());
  }

  // activate SO_KEEPALIVE on the tcp socket
  result = ipSetSocketOption(tcpSocket, "SOL_SOCKET", "SO_KEEPALIVE", 1);
  if( result != 0 )
  {
    ipGetLastSocketErrorAsString(tcpSocket, errorMessage, elcount(errorMessage));
    write("Failed to set socket option SO_KEEPALIVE. Error: %s", errorMessage);
  }

  // set Time to live it is greater than 32
  result = ipGetSocketOption(tcpSocket, "IPPROTO_IP", "IP_TTL", value);
  if( result != 0 )
  {
    ipGetLastSocketErrorAsString(tcpSocket, errorMessage, elcount(errorMessage));
    write("Failed to get socket option IP_TTL. Error: %s", errorMessage);
  }
  if( value > 32 )
  {
    result = ipSetSocketOption(tcpSocket, "IPPROTO_IP", "IP_TTL", 32);
    if( result != 0 )
    {
      ipGetLastSocketErrorAsString(tcpSocket, errorMessage, elcount(errorMessage));
      write("Failed to set socket option IP_TTL. Error: %s", errorMessage);
    }
  }

  // avoid tcp to use the nagle algorithm
  result = ipSetSocketOption(tcpSocket, "IPPROTO_TCP", "TCP_NODELAY", 1);
  if( result != 0 )
  {
    ipGetLastSocketErrorAsString(tcpSocket, errorMessage, elcount(errorMessage));
    write("Failed to get socket option TCP_NODELAY. Error: %s", errorMessage);
  }

  // connect the socket
  result = tcpConnect(tcpSocket, IpGetAddressAsNumber("192.168.1.2"), 21);
  if( result != 0 )
  {
    ipGetLastSocketErrorAsString(tcpSocket, errorMessage, elcount(errorMessage));
    write("Failed to get socket option TCP_NODELAY. Error: %s", errorMessage);
  }
}
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
