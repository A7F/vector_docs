[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Objects/CAPLfunctionIPAdredress.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **IP_Address**

# IP_Address

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

## Function Syntax

`IP_Address <addr> <var name>; // form 1`

`IP_Address <var name>; //form 2`

## Method Syntax

- [IP_Address::IsIPv4Address](../Methods/CAPLfunctionIsIPv4Address.md)
- [IP_Address::IsIPv6Address](../Methods/CAPLfunctionIsIPv6Address.md)
- [IP_Address::IsBroadcast](../Methods/CAPLfunctionIsBroadcast.md)
- [IP_Address::IsMulticast](../Methods/CAPLfunctionIsMulticast.md)
- [IP_Address::GetAddressAsArray](../Methods/CAPLfunctionGetAddressAsArray.md)
- [IP_Address::SetAddressAsArray](../Methods/CAPLfunctionSetAddressAsArray.md)
- [IP_Address::MatchesAddress](../Methods/CAPLfunctionMatchesAddress.md)
- [IP_Address::ParseAddressFromString](../Methods/CAPLfunctionParseAddressFromString.md)
- [IP_Address::PrintAddressToString](../Methods/CAPLfunctionPrintAddressToString.md)

## Description

Initializes a variable of type IP_Address with a concrete IP address (form 1) or without an IP Address (form 2).

## Parameters

- **addr**: An IPv4 or IPv6 address.
- **var name**: Character string defining the object's variable name.

## Selectors

- **IPv4Address**: Accesses the IPv4 address’ value. See [byte-order](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) of IP address.
  - Type: dword
  - Access Limitation: —
  
- **ScopeID**: ScopeID for an IPv6 address.
  - Type: dword
  - Access Limitation: —

## Example

```plaintext
variables
{
  IP_Address 192.168.0.1 ipv4Addr;
  IP_Address ff::1       ipv6Addr;
  IP_Address [ff::2]     ipv6Addr2;
  IP_Address 0.0.0.0     ipv4AnyAddr;
  IP_Address ::          ipv6AnyAddr;
}

on start
{
  IP_Address addr;
  addr = IP_Address(192.168.1.1);
  // ... do something with addr
}

on start
{
  DoSomething( IP_Address(192.168.1.1) );
}

void DoSomething( IP_Address addr )
{
  // ... do something with addr
}

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)