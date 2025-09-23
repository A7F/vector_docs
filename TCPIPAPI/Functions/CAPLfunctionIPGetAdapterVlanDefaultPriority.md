[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterVlanDefaultPriority.md)

**CAPL Functions** » **TCP/IP API** » **IpGetAdapterVlanDefaultPriority**

# IpGetAdapterVlanDefaultPriority

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetAdapterVlanDefaultPriority( dword ifIndex, word &retVlanDefaultPriority);
```

## Description

The function returns the VLAN priority of the adapter with the given index. If the adapter is not a VLAN interface it returns the error code WSA_INVALID_PARAMETER (87).

## Parameters

- **ifIndex**: The 1-based network interface index.
- **retVlanDefaultPriority**: The priority of the adapter.

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
  word prio;
  long result;
  adapterCount = ipGetAdapterCount();

  for(ifIndex = 1; ifIndex <= adapterCount; ifIndex++)
  {
    result = IpGetAdapterVlanDefaultPriority (ifIndex, prio);
    if(result == 0)
    {
      write("Adapter %d has VLAN priority %d", ifIndex, prio);
    }
  }
}
```
