[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnIpGetHostByName.md)

# OnIpGetHostByName

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » OnIpGetHostByName

## Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnIpGetHostByName(long result, char hostname[], dword ipv4Address[], dword count); // from 1
void OnIpGetHostByName(long result, char hostname[], byte ipv6Address[][], dword count); // from 2
```

## Description

The callback is called if a previous call of [IpGetHostByName](../Functions/CAPLfunctionIpGetHostByName.md) is returned with error code WSAEWOULDBLOCK (10035) and the dissolve of the address is completed.

## Parameters

- **result**: The result of the function. See the [Winsock 2 Error Codes](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md) for possible errors. Typical values are:
  - result: 0: The function completed successfully.
  - WSAHOST_NOT_FOUND (11001): Host not found.
- **hostname**: The hostname which was resolved by the function.
- **ipv4Address**: Array in which the determined IPv4 addresses are written.
- **ipv6Address**: Array in which the determined IPv6 addresses are written.
- **count**: Number of determined addresses.

## Return Values

—

## Example

```plaintext
//
// This example is only running when "Use TCP/IP stack of operating system"
// is selected.
//

on start
{
  long result;
  dword count;
  dword v4Addrs[10];
  char hostname[255];
  //
  // get IPv4 address of www.vector.de
  //
  count = elCount(v4Addrs);
  strncat(hostname, "www.vector.de", elcount(hostname));
  result = IpGetHostByName(hostname, v4Addrs, count);
  WriteAddresses(result, hostname, v4Addrs, count);
}

//
// callback is called when the DNS lookup has completed
//
void OnIpGetHostByName(long result, char hostname[], dword ipv4Address[], dword count)
{
  WriteAddresses(result, hostname, ipv4Address, count);
}

//
// print the address to the write window
//
void WriteAddresses(dword result, char hostname[], dword ipv4Address[], dword count)
{
  dword loop;
  char addrStr[16];
  if(result == 0)
  {
    write("IPv4 Addresses of %s:", hostname);
    for(loop = 0; loop < count; loop++)
    {
      ipGetAddressAsString(ipv4Address[loop], addrStr, elcount(addrStr));
      write("%s", addrStr);
    }
  }
  else if(result == 11001)
  {
    write("host %s not found", hostname);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
