[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/CAPLfunctionsTCPIPSocketOptions.md)

**CAPL Functions** » **TCP/IP API** » **Socket Options**

# Socket Options

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

This section describes the socket options which are applicable in the CAPL interface of CANoe. There are some differences in the socket options depending on the TCP/IP stack selection of the simulation node.

If the CANoe DE product internal or individual node network stack is selected all socket options marked with **C** are applicable.  
If the TCP/IP stack of the operating system is selected, all socket options marked with a **W** are applicable.

The socket options are grouped to different socket option levels. The following levels are available:

- [IPPROTO_IP](CAPLfunctionsTCPIPSocketOptionsIPPROTO_IP.md)
  - Socket options for the IPv4 protocol level.
- [IPPROTO_TCP](CAPLfunctionsTCPIPSocketOptionsIPPROTO_TCP.md)
  - Socket options for the TCP protocol level.
- [IPPROTO_UDP](CAPLfunctionsTCPIPSocketOptionsIPPROTO_UDP.md)
  - Socket options for the UDP protocol level.
- [IPPROTO_IPV6](CAPLfunctionsTCPIPSocketOptionsIPPROTO_IPV6.md)
  - Socket options for the IPv6 protocol level.
- [SOL_SOCKET](CAPLfunctionsTCPIPSocketOptionsSOL_SOCKET.md)
  - Socket options applicable at socket level.
- [SOL_VECTOR](CAPLfunctionsTCPIPSocketOptionsSOL_Vector.md)
  - Special socket option. Only available if the CANoe DE product global or node network stack is used.

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
