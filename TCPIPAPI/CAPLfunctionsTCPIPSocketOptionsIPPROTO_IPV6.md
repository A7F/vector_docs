[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/CAPLfunctionsTCPIPSocketOptionsIPPROTO_IPV6.md)

**CAPL Functions** » [TCP/IP API](CAPLfunctionsTCPIPOverview.md) » [Socket Options](CAPLfunctionsTCPIPSocketOptions.md) » IPPROTO_IPV6

# Socket Options: IPPROTO_IP

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

The following socket options can be set at the IPPROTO_IPV6 socket option level in CAPL. They influence the behavior of the IPv6 protocol per socket. For all BOOL typed options a non-zero value will be interpreted as TRUE.

**Stacks**

- **C**: Supported by CANoe internal network stack
- **W**: Supported by Windows network stack

## Socket Options Table

- **IPV6_UNICAST_HOPS**
  - **Set/Get**: set/get
  - **Description**: Set or get the value of the hoplimit field in the IPv6 header in outgoing unicast packets on this socket. The value has to be in the range from 0-255. On the CANoe DE product internal TCP/IP stack a value of -1 indicates that the stack will use a default value.
  - **Type**: LONG
  - **Stack**: C/W

- **IPV6_MULTICAST_IF**
  - **Set/Get**: set/get
  - **Description**: Set or get the interface for outgoing IPv6 multicast traffic.
  - **Type**: DWORD
  - **Stack**: C/W

- **IPV6_MULTICAST_HOPS**
  - **Set/Get**: set/get
  - **Description**: Set or get the value of the hoplimit field in the IPv6 header in outgoing multicast packets. The value has to be in the range from 0-255.
  - **Type**: DWORD
  - **Stack**: C/W

- **IPV6_MULTICAST_LOOP**
  - **Set/Get**: set/get
  - **Description**: This option controls whether multicast data will be received by a listening socket joined the same multicast group when it is sent on the same node.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **IPV6_V6ONLY**
  - **Set/Get**: set/get
  - **Description**: If this option is set to 1 the socket is restricted to IPv6 traffic only (default). If the option is set to 0 a socket created for the AF_INET6 address family may be used also for IPv4. For instance, an AF_INET6 wildcard listening socket will accept IPv4 traffic as well as it was from an IPv4 mapped address. Note that in this case even if there is no IPv4 listening socket on a port open the traffic to this port will be accepted from the IPv6 socket.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **IPV6_PORTRANGE**
  - **Set/Get**: set/get
  - **Description**: Select the range which is used for the unspecified port. The following values are supported:
    - IP_PORTRANGE_DEFAULT (0)
    - IP_PORTRANGE_HIGH (1)
    - IP_PORTRANGE_LOW (2)
  - **Type**: DWORD
  - **Stack**: C

- **IPV6_USE_MIN_MTU**
  - **Set/Get**: set/get
  - **Description**: Configure whether the minimal IPv6 maximum transmission unit (MTU) will be used to avoid fragmentation on sending datagrams. Possible values are:
    - -1: multicast datagrams use the minimal IPv6 MTU, unicast datagrams not.
    - 0: neither multicast datagrams nor unicast datagrams are limited to the minimal IPv6 MTU
    - 1: both multicast and unicast datagrams are limited to the minimal IPv6 MTU
  - **Type**: DWORD
  - **Stack**: C

- **IPV6_TCLASS**
  - **Set/Get**: set/get
  - **Description**: Set the value of the traffic class field in the IPv6 header.
  - **Type**: DWORD (boolean)
  - **Stack**: C

- **IPV6_DONTFRAG**
  - **Set/Get**: set/get
  - **Description**: If set TRUE the data will not be fragmented anymore.
  - **Type**: DWORD (boolean)
  - **Stack**: C

- **IPV6_BINDANY**
  - **Set/Get**: set/get
  - **Description**: It is possible to bind to any address, even one that is not bound to any interface when this option is set to a nonzero value.
  - **Type**: DWORD (boolean)
  - **Stack**: C

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
