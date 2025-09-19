[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPSetMulticastInterface.md)

**CAPL Functions** » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpSetMulticastInterface

# IpSetMulticastInterface

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpSetMulticastInterface ( dword socket, dword ifIndex );
```

## Description

Set the interface for outgoing multicast messages. Without calling this no multicast messages can be sent on the given socket. For IPv6 it is also necessary to set the **scope id** of the multicast address to the same interface index. Otherwise, the message will be dropped by the TCP/IP stack (see IPv6 example below).

To receive multicast messages, the multicast group has to be joined with [IpJoinMulticastGroup](CAPLfunctionIPJoinMulticastGroup.md) before.

To leave a multicast group, call [IpLeaveMulticastGroup](CAPLfunctionIPLeaveMulticastGroup.md).

**Note**: The function is dependent on the [selected stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md). This functionality cannot be used in connection with the [operating system TCP/IP stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md).

## Parameters

- **socket**: The socket handle.
- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code.

## Example

**Example IPv4**

```plaintext
on start
{
  const dword kVlanId = 1;
  dword socket;
  long result;
  ip_Endpoint 224.0.0.1:1234 IPv6_MulticastEp;

  // open a socket
  socket = udpOpen(ip_Endpoint(0.0.0.0:0));
  if(socket == ~0)
  {
    write("<%BASE_FILE_NAME%>: udpOpen failed (%d)", ipGetLastError());
  }

  // set the outgoing interface for multicast messages
  result = ipSetMulticastInterface(socket, ipGetAdapter(%CHANNEL%, kVlanId));
  if(result != 0)
  {
    write("<%BASE_FILE_NAME%>: ipSetMulticastInterface failed (result: %d, last socket error: %d)", result, ipGetLastSocketError(socket));
  }

  // send the multicast message
  result = udpSendTo(socket, IPv6_MulticastEp, "Hello", 5);
  if(result != 0)
  {
    write("<%BASE_FILE_NAME%>: udpSendTo failed (result: %d, last socket error: %d)", result, ipGetLastSocketError(socket));
  }

  udpClose(socket);
}
```

**Example IPv6**

```plaintext
on start
{
  const dword kVlanId = 1;
  dword socket;
  long result;
  ip_Endpoint [FF03::cafe]:1234 IPv6_MulticastEp;

  // open a socket
  socket = udpOpen(ip_Endpoint([0::0]:0));
  if(socket == ~0)
  {
    write("<%BASE_FILE_NAME%>: udpOpen failed (%d)", ipGetLastError());
  }

  // set the outgoing interface for multicast messages
  result = ipSetMulticastInterface(socket, ipGetAdapter(%CHANNEL%, kVlanId));
  if(result != 0)
  {
    write("<%BASE_FILE_NAME%>: ipSetMulticastInterface failed (result: %d, last socket error: %d)", result, ipGetLastSocketError(socket));
  }

  // for ipv6 it is necessary to also set the scope Id
  // to the same interface
  IPv6_MulticastEp.Address.ScopeID = ipGetAdapter(%CHANNEL%, kVlanId);

  // send the multicast message
  result = udpSendTo(socket, IPv6_MulticastEp, "Hello", 5);
  if(result != 0)
  {
    write("<%BASE_FILE_NAME%>: udpSendTo failed (result: %d, last socket error: %d)", result, ipGetLastSocketError(socket));
  }
  udpClose(socket);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
