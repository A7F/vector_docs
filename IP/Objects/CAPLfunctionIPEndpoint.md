[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Objects/CAPLfunctionIPEndpoint.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Endpoint

# IP_Endpoint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

## Function Syntax

- `IP_Endpoint <endpoint> <var name>;` // form 1
- `IP_Endpoint <var name>;` // form 2

## Method Syntax

- [IP_Endpoint::IsTCP](../Methods/CAPLfunctionIsTCP.md)
- [IP_Endpoint::IsUDP](../Methods/CAPLfunctionIsUDP.md)
- [IP_Endpoint::MatchesEndpoint](../Methods/CAPLfunctionMatchesEndpoint.md)
- [IP_Endpoint::ParseEndpointFromString](../Methods/CAPLfunctionParseEndpointFromString.md)
- [IP_Endpoint::PrintEndpointToString](../Methods/CAPLfunctionPrintEndpointToString.md)
- [IP_Endpoint::SetToTCP](../Methods/CAPLfunctionSetToTCP.md)
- [IP_Endpoint::SetToUDP](../Methods/CAPLfunctionSetToUDP.md)
- [IP_Endpoint::SetTransportProtocolToUnknown](../Methods/CAPLfunctionSetTransportProtocolToUnknown.md)

## Description

Initializes a variable of type IP_Endpoint with a concrete IP endpoint (form 1) or without an IP endpoint (form 2).

## Parameters

- **endpoint**: An IPv4 or IPv6 address and port number separated by a colon.
- **var name**: Character string defining the object's variable name.

## Selectors

- **PortNumber**: Accesses the port number. The byte order is host byte order.
- **IP_Address**: [IP_Address](CAPLfunctionIPAdredress.md) object representing the IP_Endpoint's IP address.

## Example

```plaintext
variables
{
  IP_Endpoint TCP:192.168.1.1:4000 ipEndpoint1;
  IP_Endpoint 192.168.1.2:4001 ipEndpoint2;
  IP_Endpoint 192.168.1.2 ipEndpoint3;
  IP_Endpoint UDP:[ff::1]:6000 ipEndpoint4;
  IP_Endpoint [ff::1]:6001 ipEndpoint5;
  IP_Endpoint ff::1 ipEndpoint6;
}

on start
{
  IP_Endpoint ep;
  ep = IP_Endpoint(192.168.1.2:4001);
  // ... do something with ep
}

on start
{
  DoSomething( IP_Address(FC00::0001) );
}

void DoSomething( IP_Address addr )
{
  if (addr.IsIPv4Address())
  {
    // ...
  }
  else if (addr.IsIPv6Address())
  {
    // ...
  }
}

on start
{
  IP_Endpoint 192.168.1.1:4000 ep1;
  IP_Endpoint 192.168.1.1:4000 ep2;
  if (ep1 == ep2)
  {
    write( "Endpoints are equal!" );
  }
}
```

[See Also](javascript:void(0);)