[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthClosedIPv6TCPConnection.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » OnAREthClosedIPv6TCPConnection, OnAREthClosedIPv4TCPConnection, OnAREthClosedTCPConnection

# OnAREthClosedIPv6TCPConnection, OnAREthClosedIPv4TCPConnection, OnAREthClosedTCPConnection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void OnAREthClosedIPv6TCPConnection(byte localIPv6Address[], dword localPort, byte remoteIPv6Address[], dword remotePort); // form 1`
- `void OnAREthClosedIPv4TCPConnection(dword localIPv4Address, dword localPort, dword remoteIPv4Address, dword remotePort); // form 2`
- `void OnAREthClosedTCPConnection(IP_Endpoint localIPEndpoint, IP_Endpoint remoteIPEndpoint); // form 3`

## Description

This callback will be called after a IL’s TCP connection has been closed.

## Parameters

- **localIPv6Address**: Local IPv6 address.
- **remoteIPv6Address**: Remote IPv6 address.
- **localIPv4Address**: Local IPv4 address.
- **remoteIPv4Address**: Remote IPv4 address.
- **localPort**: Local TCP port number.
- **remotePort**: Remote TCP port number.
- **localIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the local endpoint.
- **remoteIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the remote endpoint.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```c
void OnAREthClosedTCPConnection(IP_Endpoint localIPEndpoint, IP_Endpoint remoteIPEndpoint)
{
  char localEndpointStr[128], remoteEndpointStr[128];

  localIPEndpoint.PrintEndpointToString(localEndpointStr);
  remoteIPEndpoint.PrintEndpointToString(remoteEndpointStr);

  write("Closed connection: %s <-> %s", localEndpointStr, remoteEndpointStr);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)