[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsArray.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAddressAsArray

# IpGetAddressAsArray

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword IpGetAddressAsArray( char address[], byte ipv6Address[]);
```

## Description

The function converts an address string in colon notation to a 16 byte array with the address bytes in network order.

## Parameters

- **address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 address to be converted.
- **ipv6Address**: The array used to store the converted IPv6 address as [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).

## Return Values

- **0xFFFFFF**: The specified address string was invalid.
- **0x0**: The function completed successfully, the result is stored into an array.

## Example

```c
on start
{
  const dword IPV6_STR_SIZE = 40; // IPv6 string size
  int i;                         // loop variable
  byte ipv6Addr[16];             // IPv6 address bytes.
  dword result;                  // function result

  char ipv6AddrStr[IPV6_STR_SIZE] = "2001:DB8:85A3:8D3:1319:8A2E:370:7344";

  write("Converting IPv6 Address %s to bytes...", ipv6AddrStr);

  result = IpGetAddressAsArray( ipv6AddrStr, ipv6Addr );
  if (result == 0)
  {
    // success...
    write("IpGetAddressAsArray: returned array with IPv6 bytes:");
    for ( i=0; i<16; i++)
    {
      write("Byte %.2d = 0x%.2x", i, ipv6Addr[i]);
    }
  }
  else
  {
    writeLineEx(1, 3, "IpGetAddressAsArray: The specified address string was invalid.");
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)