[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/CAPLfunctionsTCPIPSocketOptionsSOL_Vector.md)

# Socket Options: SOL_VECTOR

[CAPL Functions](../CAPLfunctions.md) » [TCP/IP API](CAPLfunctionsTCPIPOverview.md) » [Socket Options](CAPLfunctionsTCPIPSocketOptions.md) » SOL_VECTOR

**Valid for**: CANoe DE • CANoe4SW DE

The following socket options can be set at the SOL_VECTOR option level in CAPL. They influence the behavior of the socket. For all BOOL typed options a non-zero value will be interpreted as TRUE.

**Stacks**

- **C**: Supported by CANoe internal network stack
- **W**: Supported by Windows network stack

**Socket Options**

- **SO_VLANPRIO**: set/get  
  Overwrite the default VLAN priority for a socket. if set to 0xFF the socket uses the default VLAN priority again.  
  Type: DWORD  
  Stack: C

- **TCP_SSTHRESH**: Set/get  
  Set or get the slow start threshold.  
  Type: DWORD  
  Stack: C

- **TCP_CWND**: Set/get  
  Set or get the congestion window size.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_STATE**: get  
  Get the current TCP state of this connection. Possible values are:  
  0: CLOSED  
  1: LISTEN  
  2: SYN_SENT  
  3: SYN_RECEIVED  
  4: ESTABLISHED  
  5: CLOSE_WAIT  
  6: FIN_WAIT_1  
  7: CLOSING  
  8: LAST_ACK  
  9: FIN_WAIT_2  
  10: TIME_WAIT  
  Type: DWORD  
  Stack: C

- **TCP_INFO_OPTIONS**: get  
  Options enabled on connection.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_SND_WSCALE**: get  
  RFC1323 send shift value.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_RCV_WSCALE**: get  
  RFC1323 recv shift value.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_RTO**: get  
  Retransmission timeout (usec).  
  Type: DWORD  
  Stack: C

- **TCP_INFO_SND_MSS**: get  
  Max segment size for send.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_RCV_MSS**: get  
  Max segment size for receive.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_LAST_DATA_RECV**: get  
  Time since last recv data.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_RTT**: get  
  Smoothed RTT in usecs.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_RTTVAR**: get  
  RTT variance in usecs.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_SND_SSTHRESH**: get  
  Slow start threshold.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_SND_CWND**: get  
  Send congestion window.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_RCV_SPACE**: get  
  Advertised recv window.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_SND_WND**: get  
  Advertised send window.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_SND_BWND**: get  
  Bandwidth send window.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_SND_NXT**: get  
  Next egress sequence number.  
  Type: DWORD  
  Stack: C

- **TCP_INFO_RCV_NXT**: get  
  Next ingress sequence number.  
  Type: DWORD  
  Stack: C

- **TCP_SWSAVOID**: set/get  
  Enable/disable silly window syndrome avoidance algorithm.  
  Type: DWORD  
  Stack: C

© Vector Informatik GmbH

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)