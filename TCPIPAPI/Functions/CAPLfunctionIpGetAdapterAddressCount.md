[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpGetAdapterAddressCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAdapterAddressCount

# IpGetAdapterAddressCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetAdapterAddressCount( dword ifIndex, dword addressFamily);
```

## Description

The function returns the count of addresses belonging to the given address family which are assigned to the adapter with the given index.

## Parameters

- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.

- **addressFamily**: The address family of the addresses, the address count will be returned. Possible values are:
  - AF_INET (2): IPv4 address family
  - AF_INET6 (28): IPv6 address family

## Return Values

The count of addresses of the given address family will be returned.

- **SOCKET_ERROR(-1)**: The function call failed. Invalid `ifIndex` or `addressFamily` given.

## Example

```plaintext
on start
{
  const dword AF_INET = 2;   // IPv4 adapter family
  const dword AF_INET6 = 28; // IPv6 adapter family
  dword ifIdx;               // interface index
  long ipv4AdrCount;         // variable for count of all ipv4 addresses of first adapter
  long ipv6AdrCount;         // variable for count of all ipv6 addresses of first adapter

  for (ifIdx = 1; ifIdx <= IpGetAdapterCount(); ifIdx++)
  {
    ipv4AdrCount = IpGetAdapterAddressCount( ifIdx, AF_INET );
    if (ipv4AdrCount != -1)
    {
      write("IpGetAdapterAddressCount: Adapter with index %d has %d IPv4 addresses assigned.", ifIdx, ipv4AdrCount);
    }
    else
    {
      writeLineEx(1, 3, "IpGetAdapterAddressCount: Error: The function call failed. Invalid ifIndex given for ipv4.");
    }

    ipv6AdrCount = IpGetAdapterAddressCount( ifIdx, AF_INET6 );
    if (ipv6AdrCount != -1)
    {
      write("IpGetAdapterAddressCount: Adapter with index %d has %d IPv6 addresses assigned.", ifIdx, ipv6AdrCount);
    }
    else
    {
      writeLineEx(1, 3, "IpGetAdapterAddressCount: Error: The function call failed. Invalid ifIndex given for ipv6.");
    }
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)