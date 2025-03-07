# Socket Options: IPPROTO_IP

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/CAPLfunctionsTCPIPSocketOptionsIPPROTO_IP.md)

**CAPL Functions** » **TCP/IP API** » **Socket Options** » IPPROTO_IP

**Valid for**: CANoe DE • CANoe4SW DE

The following socket options can be set at the IPPROTO_IP socket option level in CAPL. They influence the behavior of the IPv4 protocol per socket. For all BOOL typed options a non-zero value will be interpreted as TRUE.

**Stacks**

- **C**: Supported by CANoe internal network stack
- **W**: Supported by Windows network stack

## Socket Options

- **IP_TOS**
  - **Set/Get**: set/get
  - **Description**: Set or get the Type of Service field in the IPv4 protocol in outgoing datagrams on this socket. The value has to be in the range from 0-255.
  - **Type**: DWORD
  - **Stack**: C/W

- **IP_TTL**
  - **Set/Get**: set/get
  - **Description**: Set or get the value of the TTL field of the IP header in outgoing datagrams on this socket. The value has to be in the range from 0-255.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **IP_MULTICAST_TTL**
  - **Set/Get**: set/get
  - **Description**: Set or get the value of the TTL field for IPv4 multicast traffic on this socket.
  - **Type**: DWORD
  - **Stack**: C/W

- **IP_MULTICAST_LOOP**
  - **Set/Get**: set/get
  - **Description**: This option controls whether multicast data will be received by a listening socket joined the same multicast group when it is sent on the same node.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **IP_DONTFRAGMENT**
  - **Set/Get**: set/get
  - **Description**: If set to TRUE the don’t fragment flag in the IP header is set and data will not be fragmented anymore. This is only available for UDP sockets.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **IP_RECEIVE_BROADCAST**
  - **Set/Get**: set/get
  - **Description**: Allows or disables the reception of broadcast messages. Only for UDP sockets.
  - **Type**: DWORD (boolean)
  - **Stack**: W

- **IP_PORTRANGE**
  - **Set/Get**: set/get
  - **Description**: Select the range which is used for the unspecified port. The following values are supported:
    - IP_PORTRANGE_DEFAULT (0)
    - IP_PORTRANGE_HIGH (1)
    - IP_PORTRANGE_LOW (2)
  - **Type**: DWORD
  - **Stack**: C

- **IP_ONESBCAST**
  - **Set/Get**: set/get
  - **Description**: When this option is set on a UDP Socket the destination address of outgoing broadcast datagrams will be set to the undirected broadcast address.
  - **Type**: DWORD (boolean)
  - **Stack**: C

- **IP_BINDANY**
  - **Set/Get**: set/get
  - **Description**: It is possible to bind to any address, even one that is not bound to any interface when this option is set to a nonzero value.
  - **Type**: DWORD (boolean)
  - **Stack**: C

- **IP_MINTTL**
  - **Set/Get**: set/get
  - **Description**: Set the minimum acceptable TTL value which a packet must have when it is received. If the TTL value is lower, the packet will be dropped.
  - **Type**: DWORD
  - **Stack**: C

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)