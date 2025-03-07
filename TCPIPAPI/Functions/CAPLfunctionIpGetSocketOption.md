[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpGetSocketOption.md)

**CAPL Functions** » **TCP/IP API** » **IpGetSocketOption**

# IpGetSocketOption

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetSocketOption( dword socket, char level[], char name[], long &value);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
socket.GetSocketOption(char level[], char name[], long &value);
```

## Description

The function reads the value of the given [socket option](../CAPLfunctionsTCPIPSocketOptions.md).

The function is dependent on the [selected stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md).

## Parameters

- **socket**: The socket handle.
- **level**: The level at which the option is defined, e.g. SOL_SOCKET (0xFFFF). See [Socket Options](../CAPLfunctionsTCPIPSocketOptions.md) for all supported socket levels.
- **name**: The socket option name to be read, e.g. SO_BROADCAST (0x0020). See [Socket Options](../CAPLfunctionsTCPIPSocketOptions.md) for all supported socket options.
- **value**: The value of the socket option will be returned in this variable.

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket index was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code.

## Example

```plaintext
on start
{
  char errorMessage[255];
  long socket;
  long result;
  long value;

  // open a udp socket
  socket = udpOpen(0,0);
  if( socket == ~0 )
  {
    write("open udp socket failed. Last error was %d", ipGetLastError());
  }

  // get the socket type (UDP = 2, TCP = 1)
  result = ipGetSocketOption(socket, "SOL_SOCKET", "SO_TYPE", value);
  if( result != 0 )
  {
    ipGetLastSocketErrorAsString(socket, errorMessage, elcount(errorMessage));
    write("Failed to get socket option SO_TYPE. Error: %s", errorMessage);
  }
  else
  {
    write("The socket type is %d", value);
  }
  result = ipGetSocketOption(socket, "IPPROTO_IP", "IP_TTL", value);
  if( result != 0 )
  {
    ipGetLastSocketErrorAsString(socket, errorMessage, elcount(errorMessage));
    write("Failed to get socket option IP_TTL. Error: %s", errorMessage);
  }
  else
  {
    write("The IP TTL of this socket is %d", value);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)