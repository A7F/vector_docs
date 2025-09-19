[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpSetStackParameter.md)

**CAPL Functions** » **TCP/IP API** » **IpSetStackParameter**

# IpSetStackParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long IpSetStackParameter(char parameterName[], long value); // form 1`
- `long IpSetStackParameter(dword ifIndex, char parameterName[], long value); // form 2`

## Description

With this function, it is possible to modify the general behavior of the TCP/IP Stack or the behavior of an interface of the TCP/IP Stack. The name of the parameter is given as a path separated by dots.

The following values can be set by the function:

- **canoe.interface.mtu**: Changes the size of the interface maximum transmission unit. This value has to be in the range between 72 and 1500 Byte. An interface index must be given to set this value. Default Value: 1500, Form: form 2
- **canoe.ipv6.default_scope**: Sets the default scope of the ipv6 stack. The default scope is used when the destination address is a link local address. Default Value: 0, Form: form 1
- **net.inet.ip.ttl**: IPv4: Changes the default max number of hops used for unicast packets. Default Value: 64, Form: form 1
- **net.inet.tcp.delacktime**: Time before a delayed ACK is sent. Default Value: 100 ms, Form: form 1
- **net.inet.tcp.delayed_ack**: Deactivates or activate the delayed acknowledge algorithm of TCP. By default, this parameter is enabled so that TCP tries to send the ACK flag piggyback on the next responding packet. Default Value: 1, Form: form 1
- **net.inet.tcp.hostcache.purgenow**: Clears all metrics which are collected in the TCP hostcache e.g. the slow start threshold for an existing route. Default Value: -, Form: form 1
- **net.inet.tcp.rexmit_base**: Initial Retransmission Timeout of TCP connections. Default Value: 3000 ms, Form: form 1
- **net.inet.tcp.rexmit_max**: Maximum retransmission timeout of TCP connections. Default Value: 64000 ms, Form: form 1
- **net.inet.tcp.rexmit_min**: Minimum Retransmission Timeout of TCP connections. Default Value: 30 ms, Form: form 1
- **net.inet.tcp.rfc1323**: Deactivates or activates the TCP timestamp option according to RFC1323. By default, this parameter is enabled since version 12.0. Default Value: 1, Form: form 1
- **net.inet.tcp.sws_avoid**: Enable/disable the silly window syndrome avoidance algorithm. This changes the default value for new sockets. Default Value: 1, Form: form 1
- **net.inet6.ip6.defmcasthlim**: IPv6: Changes the default max number of hops used for multicast packets. Default Value: 1, Form: form 1
- **net.inet6.ip6.hlim**: IPv6: Changes the default max number of hops used for unicast packets. Default Value: 64, Form: form 1

**Note:**

- The function depends on the selected stack.
- This functionality cannot be used in connection with the operating system TCP/IP stack.

## Parameters

- **ifIndex**: The 1-based network interface index.
- **parameterName**: A string representing the path to the parameter which should be set (e.g. **net.inet.tcp.delayed_ack**).
- **value**: The value that should be set.

## Return Values

- **0**: The function completed successfully.
- **1**: The function is not supported on the selected TCP/IP stack.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

## Example

```plaintext
on start
{
  LONG result;
  LONG ifIndex;
  LONG value;

  // change maximum transmission unit of interface given in ifIndex
  ifIndex = 1;
  value = 1460;
  result = ipSetStackParameter(ifIndex, "canoe.interface.mtu", value);
  if(result != 0) {
    writeLineEx(1, 3, "Failed to set mtu of interface %d to %d byte. Result: %d", ifIndex, value, result);
  }
  else {
    writeLineEx(1, 0, "Set MTU of interface %d to %d byte.", ifIndex, value);
  }

  // change the ipv6 default scope to the interface given in ifIndex
  result = ipSetStackParameter("canoe.ipv6.default_scope", 1);
  if(result != 0) {
    writeLineEx(1, 3, "Failed to set ipv6 default scope to interface %d. Result: %d", ifIndex, result);
  }
  else {
    writeLineEx(1, 0, "Set ipv6 default scope to interface %d.", ifIndex);
  }

  // change the tcp delayed acknowledge behavior
  value = 0;
  result = ipSetStackParameter("net.inet.tcp.delayed_ack", value);
  if(result != 0) {
    writeLineEx(1, 3, "Failed to change delayed acknowledge behavior. Result: %d", result);
  }
  else {
    if( value == 0){
      writeLineEx(1, 0, "Successfully disabled TCP delayed acknowledge");
    }
    else{
      writeLineEx(1, 0, "Successfully enabled TCP delayed acknowledge");
    }
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
