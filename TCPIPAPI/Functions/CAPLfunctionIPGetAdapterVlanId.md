[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterVlanId.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAdapterVlanId

# IpGetAdapterVlanId

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetAdapterVlanId( dword ifIndex, word &retVlanId);
```

## Description

The function returns the VLAN ID of the adapter with the given index. If the adapter is not a VLAN interface it returns the error code WSA_INVALID_PARAMETER (87).

## Parameters

- **ifIndex**: The 1-based network interface index.
- **retVlanId**: The VLAN ID of the adapter.

## Return Values

- **0**: The function completed successfully.
- **1**: The function is not supported on the selected TCP/IP stack.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid or is not a VLAN adapter.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

## Example

```plaintext
on start
{
  dword adapterCount;
  dword ifIndex;
  word vlanId;
  long result;
  adapterCount = ipGetAdapterCount();

  for(ifIndex = 1; ifIndex <= adapterCount; ifIndex++)
  {
    result = ipGetAdapterVlanId(ifIndex, vlanId);
    if(result == 0)
    {
      write("Adapter %d has VLAN id %d", ifIndex, vlanId);
    }
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
