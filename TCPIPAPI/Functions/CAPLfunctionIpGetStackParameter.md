[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpGetStackParameter.md)

## CAPL Functions » TCP/IP API » IpGetStackParameter

### Function Syntax

- `long IpGetStackParameter(char parameterName[], long &value); // form 1`
- `long IpGetStackParameter(dword ifIndex, char parameterName[], long &value); // form 2`

### Description

With this function, it is possible to read the value of a TCP/IP Stack parameter. The name of the parameter is given as a path separated by dots.

The following values can be read by the function:

- **canoe.interface.mtu**: Gets the size of the interface maximum transmission unit. An interface index must be given to get this value. Default: 1500, Form: form 2
- **canoe.ipv6.default_scope**: Gets the default scope of the ipv6 stack. The default scope is used when the destination address is a link local address. Default: 0, Form: form 1
- **net.inet.tcp.delayed_ack**: Checks if the delayed acknowledge algorithm of TCP is activated or deactivated. By default, this parameter is enabled so that TCP tries to send the ACK flag piggyback on the next responding packet. Default: 1, Form: form 1
- **net.inet.tcp.delacktime**: Time before a delayed ACK is sent. Default: 100 ms, Form: form 1
- **net.inet.tcp.rfc1323**: Checks if RFC1323 extensions are enabled. By default, this parameter is enabled since Version 12.0. Default: 1, Form: form 1
- **net.inet.tcp.rexmit_max**: Gets the maximum retransmission timeout of TCP connections. Default: 64000 ms, Form: form 1
- **net.inet.tcp.rexmit_min**: Minimum Retransmission Timeout of TCP connections. Default: 30 ms, Form: form 1
- **net.inet.tcp.rexmit_base**: Initial Retransmission Timeout of TCP connections. Default: 3000 ms, Form: form 1

**Note:**

- The function depends on the selected stack.
- This functionality cannot be used in connection with the operating system TCP/IP stack.

### Parameters

- **ifIndex**: The 1-based network interface index.
- **parameterName**: A string representing the path to the parameter which should be set (e.g. `net.inet.tcp.delayed_ack`).
- **&value**: The value of the parameter that will be returned.

### Return Values

- **0**: The function completed successfully.
- **1**: The function is not supported on the selected TCP/IP stack.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

### Example

```c
on start
{
  LONG result;
  LONG ifIndex;
  LONG value;

  // get the maximum transmission unit of the interface given in ifIndex
  ifIndex = 1;
  result = ipGetStackParameter(ifIndex, "canoe.interface.mtu", value);
  if(result != 0) {
    writeLineEx(1, 3, "Failed to get mtu of interface %d. Result: %d", ifIndex, result);
  }
  else {
    writeLineEx(1, 0, "MTU of interface %d is %d byte.", ifIndex, value);
  }

  // get the ipv6 default scope
  result = ipGetStackParameter("canoe.ipv6.default_scope", value);
  if(result != 0) {
    writeLineEx(1, 3, "Failed to get ipv6 default scope. Result: %d", result);
  }
  else {
    writeLineEx(1, 0, "IPv6 default scope is set to interface %d.", value);
  }

  // get the tcp delayed acknowledge behavior
  result = ipGetStackParameter("net.inet.tcp.delayed_ack", value);
  if(result != 0) {
    writeLineEx(1, 3, "Failed to get delayed acknowledge behavior. Result: %d", result);
  }
  else {
    if( value == 0){
      writeLineEx(1, 0, "TCP delayed acknowledge is disabled");
    }
    else{
      writeLineEx(1, 0, "TCP delayed acknowledge is enabled");
    }
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
