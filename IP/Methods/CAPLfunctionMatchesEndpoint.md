[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionMatchesEndpoint.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Endpoint::MatchesEndpoint

# IP_Endpoint::MatchesEndpoint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

- `long IP_Endpoint::MatchesEndpoint(IP_Endpoint ipEndpoint);` // form 1
- `long IP_Endpoint::MatchesEndpoint(IP_Endpoint ipEndpoint, long prefix);` // form 2

## Description

Compares two endpoints whereas wildcards matches always. If no transport protocol type is set or the port number is set to 0 this is considered as wildcard. Additionally, the IP address must match according to [MatchesAddress](CAPLfunctionMatchesAddress.md).

With form 2 only the network address of the IP address will be considered.

## Parameters

- **ipEndpoint**: An IP endpoint that may contain wildcards.
- **prefix**: Prefix in number of bits. Only the first bits specified by prefix are considered.

## Return Values

- **0**: No match
- **1**: Matches

## Example

**Example 1**

```plaintext
on start
{
  IP_Endpoint 192.168.1.1:4000 ep1;
  IP_Endpoint 192.168.1.2:4000 ep2;
  if (ep1.MatchesEndPoint( ep2 ) == 1)
  {
    write( "Endpoints match!" );
  }
}
```

**Example 2**

```plaintext
on start
{
  IP_Endpoint 192.168.1.1:4000 ep1;
  IP_Endpoint 192.168.1.2:4000 ep2;
  if (ep1.MatchesEndPoint( ep2, 24 ) == 1)
  {
    write( "Endpoints match!" );
  }
}
```

**Example 3**

```plaintext
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
