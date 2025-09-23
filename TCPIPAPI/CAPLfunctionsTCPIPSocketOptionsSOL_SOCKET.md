[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/CAPLfunctionsTCPIPSocketOptionsSOL_SOCKET.md)

# Socket Options: SOL_SOCKET

[CAPL Functions](../CAPLfunctions.md) » [TCP/IP API](CAPLfunctionsTCPIPOverview.md) » [Socket Options](CAPLfunctionsTCPIPSocketOptions.md) » SOL_SOCKET

**Valid for**: CANoe DE • CANoe4SW DE

The following socket options can be set at the SOL_SOCKET option level in CAPL. They influence the behavior of the socket. For all BOOL typed options a non-zero value will be interpreted as TRUE.

**Stacks**

- **C**: Supported by CANoe internal network stack
- **W**: Supported by Windows network stack

**Socket Options**

- **SO_DEBUG**
  - **Set/Get**: set/get
  - **Description**: Activates the recording of debugging information. CANoe DE product currently do not output any debug information.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **SO_ACCEPTCONN**
  - **Set/Get**: get
  - **Description**: Returns if a socket is in listening mode. This only works for connection orientated protocols like TCP.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **SO_REUSEADDR**
  - **Set/Get**: set/get
  - **Description**: Allow local address and port reuse. But even if two sockets are bound to the same port the behavior which socket receives the packet is undefined.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **SO_KEEPALIVE**
  - **Set/Get**: set/get
  - **Description**: Enables keep connections alive for a socket connection. Only valid for connection orientated protocols like TCP. The default keep alive timeout is 2 hours.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **SO_DONTROUTE**
  - **Set/Get**: set/get
  - **Description**: If this option is enabled, the socket can only send in a local network. The routing to the default gateway is disabled.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **SO_BROADCAST**
  - **Set/Get**: set/get
  - **Description**: Enable sending broadcast data on a socket. This option is only valid for UDP sockets. The option set by default during [udpOpen](Functions/CAPLfunctionUDPOpen.md).
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **SO_OOBINLINE**
  - **Set/Get**: set/get
  - **Description**: Activates the reception of out-of-band data in band. This option is only allowed on TCP sockets.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **SO_SNDBUF**
  - **Set/Get**: set/get
  - **Description**: Set the size of the buffers for outgoing data.
  - **Type**: DWORD
  - **Stack**: C/W

- **SO_RCVBUF**
  - **Set/Get**: set/get
  - **Description**: Set the size of the buffers for incoming data.
  - **Type**: DWORD
  - **Stack**: C/W

- **SO_SNDLOWAT**
  - **Set/Get**: set/get
  - **Description**: Set the minimum count of data for output.
  - **Type**: DWORD
  - **Stack**: C

- **SO_RCVLOWAT**
  - **Set/Get**: set/get
  - **Description**: Set the minimum count of data for input.
  - **Type**: DWORD
  - **Stack**: C

- **SO_ERROR**
  - **Set/Get**: get
  - **Description**: Get the last error code on this socket.
  - **Type**: DWORD
  - **Stack**: C/W

- **SO_TYPE**
  - **Set/Get**: get
  - **Description**: Returns the socket type of this socket. For UDP sockets 2 is returned. For TCP sockets 1 is returned.
  - **Type**: DWORD
  - **Stack**: C/W

- **SO_EXCLUSIVEADDRUSE**
  - **Set/Get**: set/get
  - **Description**: If this option is set its not possible for any other socket to bind to the same address and port.
  - **Type**: DWORD
  - **Stack**: W

- **SO_DONTLINGER**
  - **Set/Get**: set/get
  - **Description**: If option is set to 0 a connected socket will abort immediately. If option is set to 1 a connected socket will send all pending data first and will then initiate the shutdown sequence. On a windows socket the port will be unavailable for new socket connections until the socket moves from TIME_WAIT state to CLOSED state.
  - **Type**: DWORD
  - **Stack**: C/W
