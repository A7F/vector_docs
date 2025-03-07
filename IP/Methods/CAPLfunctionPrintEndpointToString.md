[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionPrintEndpointToString.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Endpoint::PrintEndpointToString

# IP_Endpoint::PrintEndpointToString

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

long [IP_Endpoint](../Objects/CAPLfunctionIPEndpoint.md)::PrintEndpointToString(char endpoint[]);

## Description

Converts the endpoint to a character string with the following form:
`<TCP/UCP>:<ip_Address>:<Port>`

**Examples**:

- IPv4 Endpoint: 192.168.1.1:100
- IPv4 TcpEndpoint: TCP:192.168.1.1:100
- IPv6 Endpoint: [2001:DB8::1]:100
- IPv6 TcpEndpoint mit ScopeId: TCP:[2001:DB8::1%1]:100
- IPv6 UdpEndpoint: UDP:[2001:DB8::1]:100

## Parameters

- **endpoint**: A character string representing an IP endpoint.

## Return Values

- **0**: Success
- **1**: Character string too small

## Example

```c
void OnReceiveFrom(UdpSocket socket, long result, IP_Endpoint senderEndpoint, byte buffer[], dword size)
{
  char endpointText[60];
  senderEndpoint.PrintEndpointToString(endpointText);
  write("packet from %s received", endpointText);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)