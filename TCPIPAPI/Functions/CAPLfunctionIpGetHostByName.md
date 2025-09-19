[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpGetHostByName.md)

**CAPL Functions** » **TCP/IP API** » **IpGetHostByName**

# IpGetHostByName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long IpGetHostByName(char hostname[],dword ipv4Address[], dword &count); // form 1`
- `long IpGetHostByName(char hostname[],byte ipv6Address [][], dword &count); // form 2`
- `long IpGetHostByName(char hostname[], IP_Address addresses[], dword &count ); // form 3`

## Description

The function dissolves a host name in its IP address. The given host name is first searched in the CANoe DE product Simulation Setup and then in the assigned database. If the name is not defined there, it is determined via a DNS request by using the operating system stack. For this, the operating system stack must be selected in the CANoe DE product [TCP/IP Stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md) configuration dialog. The result is then given back in the corresponding callback [OnIpGetHostByName](../EventProcedures/CAPLfunctionTCPIPOnIpGetHostByName.md).

## Parameters

- **hostname**: The name of the host whose address should be determined.
- **ipv4Address**: Array in which the determined IPv4 addresses are written.
- **ipv6Address**: Array in which the determined IPv6 addresses are written.
- **count**:
  - On call: buffer size (only form 1-2)
  - After call: Number of determined addresses
- **addresses**: Array of IP_Address elements, which is filled with the IP addresses (IPv4 and IPv6) for the host.

## Return Values

- **0**: The function completed successfully.
- **ERROR_NOT_ENOUGH_MEMORY (8)**: The given address array is too small.
- **WSAEWOULDBLOCK (10035)**: The function will be completed later and the callback is called.
- **WSAHOST_NOT_FOUND (11001)**: Host not found.

## Example

```c
//
// This example expects a node with the name ECU 1 in the
// Simulation Setup.
//
on start
{
  char addrStr[47];
  long result;
  dword count;
  dword loop;
  dword v4Addrs[10];
  byte  v6Addrs[10][16];

  //
  // get IPv4 addresses of node ECU 1
  //
  count = elCount(v4Addrs);
  result = IpGetHostByName("ECU 1", v4Addrs, count);
  if(result == 0)
  {
    write("IPv4 Addresses of Node ECU 1:");
    for(loop = 0; loop < count; loop++)
    {
      ipGetAddressAsString(v4Addrs[loop], addrStr, elcount(addrStr));
      write("%s", addrStr);
    }
  }

  //
  // get IPv6 addresses of node ECU 1
  //
  count = elCount(v6Addrs);
  result = IpGetHostByName("ECU 1", v6Addrs, count);
  if(result == 0)
  {
    write("IPv6 Addresses of Node ECU 1:");
    for(loop = 0; loop < count; loop++)
    {
      ipGetAddressAsString(v6Addrs[loop], addrStr, elcount(addrStr));
      write("%s", addrStr);
    }
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
