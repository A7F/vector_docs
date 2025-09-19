[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionMatchesAddress.md)

# IP_Address::MatchesAddress

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Address::MatchesAddress

## Method Syntax

- `long IP_Address::MatchesAddress (IP_Address ipAddr); // form 1`
- `long IP_Address::MatchesAddress (IP_Address ipAddr, long prefix); // form 2`
- `long IP_Address::MatchesAddress (IP_Address ipAddr, IP_Address netMask); // form 3`

### Description

Compares two addresses whereas wildcards matches always. If no address type is set or the address is set to `0.0.0.0 (IPv4)` or `::0 (IPv6)` this is considered as wildcard.

With form 2 only the network address of the IP address will be considered.

With forms 2 and 3, only the network address of the IP address will be considered.

### Parameters

- **ipAddr**: An IP_Address object which may contain wildcards.
- **prefix**: Prefix in number of bits. Only the first bits specified by prefix are considered.
- **netMask**: Network mask of the subnet. A bitwise AND operation is used to determine which bits of the address are considered. Addresses and mask must use the same version of the IP protocol.

### Return Values

- **0**: No match
- **1**: Match

### Example

**Example 1**

```plaintext
on start
{
  IP_Address 192.168.1.1 addr1;
  IP_Address 192.168.1.2 addr2;
  if (addr1.MatchesAddress( addr2 ) == 1)
  {
    write( "Address match!" );
  }
}
```

**Example 2**

```plaintext
on start
{
  IP_Address 192.168.1.1 addr1;
  IP_Address 192.168.1.2 addr2;
  if (addr1.MatchesAddress( addr2, 24 ) == 1)
  {
    write( "Address match!" );
  }
}
```

**Example 3**

```plaintext
on start
{
  IP_Address 192.168.1.1 addr1;
  IP_Address 192.168.1.2 addr2;
  if (addr1 == addr2)
  {
    write( "Addresses are equal!" );
  }
  else
  {
    write( "Addresses are not equal!" );
  }
}
```

**Example 4**

```plaintext
on start
{
  IP_Address 192.168.1.1 addr1;
  IP_Address 192.168.1.2 addr2;
  IP_Address 255.255.255.0 netMask;
  if (addr1.MatchesAddress( addr2, netMask ))
  {
    write( "Addresses are equal!" );
  }
  else
  {
    write( "Addresses are not equal!" );
  }
}
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
