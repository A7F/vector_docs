[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsString.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAddressAsString

# IpGetAddressAsString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetAddressAsString( dword numericAddress, char address[], dword count); // from 1
long IpGetAddressAsString( byte ipv6Address[], char address[], dword count); // from 2
```

## Description

The function converts a numeric address in [network-byte order (big endian)](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) to an address string in dot notation as in "192.168.0.10". For IPv6, the address string has to contain a string in colon notation as in "1234:5678:9ABC:DEF1:2345:6789:ABCD:EF12".

## Parameters

- **numericAddress**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 address to be converted.
- **ipv6Address**: The local IPv6 address in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **address**: The buffer used to store the converted IPv4 address.
- **count**: The size of the address buffer.

## Return Values

- **0**: The function completed successfully.
- **ERROR_NOT_ENOUGH_MEMORY (8)**: The address buffer was insufficient.
- **WSA_INVALID_PARAMETER (87)**: The specified address was invalid.

## Example

```plaintext
on start
{
  const dword IPV4_STR_SIZE = 16;   // IPv4 string size
  const dword IPV6_STR_SIZE = 40;   // IPv6 string size
  dword ipv4Addr = 0xde6fa881;      // an IPv4Addr (192.168.111.222)
  char ipv4AddrStr[IPV4_STR_SIZE];  // an IPv4Addr string buffer
  char ipv6AddrStr[IPV6_STR_SIZE];  // an IPv6Addr string buffer
  long result;                      // function result;
  byte ipv6Addr[16] = {0x20,0x01,0x0D,0xB8,0x85,0xA3,0x08,0xD3,0x13,0x19,0x8A,0x2E,0x03,0x70,0x73,0x44}; // an IPv6 Addr (2001:DB8:85A3:8D3:1319:8A2E:370:7344)

  result = IpGetAddressAsString( ipv4Addr, ipv4AddrStr, elcount(ipv4AddrStr) );
  if (result == 0)
  {
    write("IpGetAddressAsString: Address 0x%x => %s", ipv4Addr, ipv4AddrStr);
  }
  else
  {
    writeLineEx(1, 3, "IpGetAddressAsString: Error %d", result);
  }

  result = IpGetAddressAsString( ipv6Addr, ipv6AddrStr, elcount(ipv6AddrStr) );
  if (result == 0)
  {
    write("IpGetAddressAsString: IPv6 address bytes => %s", ipv6AddrStr);
  }
  else
  {
    writeLineEx(1, 3, "IpGetAddressAsString: Error %d", result);
  }
}
```
