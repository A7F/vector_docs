# Socket Options: IPPROTO_TCP

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/CAPLfunctionsTCPIPSocketOptionsIPPROTO_TCP.md)

**CAPL Functions** » **TCP/IP API** » **Socket Options** » IPPROTO_TCP

**Valid for**: CANoe DE • CANoe4SW DE

The following socket options can be set at the IPPROTO_TCP socket option level in CAPL. They influence the behavior of the TCP protocol per socket. For all BOOL typed options a non-zero value will be interpreted as TRUE.

**Stacks**

- **C**: Supported by CANoe internal network stack
- **W**: Supported by Windows network stack

### Socket Options

- **TCP_NODELAY**
  - **Set/Get**: set/get
  - **Description**: The Nagle algorithm for TCP sockets will be disabled if this option is set to a non-zero value. The Nagle algorithm collects small amounts of output data to send in a single packet if outstanding data has not yet been acknowledged.
  - **Type**: DWORD (boolean)
  - **Stack**: C/W

- **TCP_MAXSEG**
  - **Set/Get**: C:set/get, W: get
  - **Description**: The maximum segment size is normally negotiated between sender and receiver. This option allows to check the result of this operation and to reduce it.
  - **Type**: DWORD
  - **Stack**: C/W

- **TCP_NOOPT**
  - **Set/Get**: set/get
  - **Description**: Avoid the TCP protocol to send TCP options.
  - **Type**: DWORD (boolean)
  - **Stack**: C

- **TCP_NOPUSH**
  - **Set/Get**: set/get
  - **Description**: Normally the push flag is set and the data is sent immediately on the end of every user call to [TcpSend](Functions/CAPLfunctionTCPSend.md). When the option is set to a non-zero value, TCP will delay sending any data until either the socket is closed, or the internal send buffer is filled.
  - **Type**: DWORD (boolean)
  - **Stack**: C

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)