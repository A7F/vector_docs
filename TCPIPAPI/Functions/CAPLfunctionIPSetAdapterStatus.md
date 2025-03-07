[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPSetAdapterStatus.md)

# IPSetAdapterStatus

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IPSetAdapterStatus

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This function is only available when the Individual TCP/IP stack instance or CANoe TCP/IP Stack is used.

## Function Syntax

```plaintext
long IPSetAdapterStatus( dword ifIndex, dword status);
```

## Description

With this function, it is possible to activate or deactivate a network adapter of the TCP/IP stack.

- When the adapter is set down, all IP addresses of this adapter will be removed, and sending or receiving packets on this adapter will be stopped.
- If the default gateway was configured in a network which was configured on this adapter, it will also be removed.
- When the adapter is set up again, the addresses configured in the TCP/IP Stack dialog will be reconfigured, and the default gateway is set again.

## Parameters

- **ifIndex**: The 1-based network interface index.
- **status**: 
  - 0: Set adapter down
  - 1: Set adapter up

## Return Values

- **0**: The function completed successfully.
- **1**: The function is not supported on the selected TCP/IP stack.
- **WSA_INVALID_PARAMETER (87)**: Invalid parameter given
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)