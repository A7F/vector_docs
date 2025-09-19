[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPSetAdapterMacId.md)

# IpSetAdapterMacId

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpSetAdapterMacId

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
long IpSetAdapterMacId( dword ifIndex, qword macId);
```

## Description

Sets the mac id of the given interface.

## Parameters

- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.

- **macId**: The MAC address as qword.

## Return Values

- **0**: The function completed successfully.
- **1**: The function is not supported on the selected TCP/IP stack.
- **WSA_INVALID_PARAMETER (87)**: Invalid parameter given.

## Example

```plaintext
on start
{
  dword result;
  dword channel = 1;
  dword ifIndex;
  qword macId;

  ifIndex = ipGetAdapter(channel);
  if(ifIndex > 0)
  {
    macId = ethGetMacAddressAsNumber("02:11:22:33:44:55");
    result = ipSetAdapterMacId(ifIndex, macId);
    if(result != 0)
    {
      write("ipSetAdapterMacId for interface %d failed", ifIndex);
    }
  }
  else
  {
    write("No interface found for channel %d", channel);
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
