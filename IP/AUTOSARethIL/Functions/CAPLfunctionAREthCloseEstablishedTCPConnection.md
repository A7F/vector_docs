# AREthCloseEstablishedTCPConnection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AREthCloseEstablishedTCPConnection (); // form 1`
- `dword AREthCloseEstablishedTCPConnection (dword aepHandle); // form 2`
- `dword AREthCloseEstablishedTCPConnection (dword aepHandle, dword remoteIPv4Address); // form 3`
- `dword AREthCloseEstablishedTCPConnection (dword aepHandle, dword remoteIPv4Address, dword remotePort); // form 4`
- `dword AREthCloseEstablishedTCPConnection (dword aepHandle, byte remoteIPv6Address[]); // form 5`
- `long AREthCloseEstablishedTCPConnection (dword aepHandle, byte remoteIPv6Address[], dword remotePort); // form 6`
- `long AREthCloseEstablishedTCPConnection (dword aepHandle, IP_Endpoint remoteIPEndpoint); // form 7`

## Description

Closes one or multiple database defined TCP connection(s).

- **Form 1:** Closes all TCP connections of this node (as TCP client)
- **Form 2:** Closes all TCP connections of TCP client
- **Form 3/5:** Closes all TCP connections of TCP client to specific TCP server
- **Form 4/6:** Closes TCP connection of TCP client to specific TCP server

A TCP connection can be opened using the [AREthEstablishTCPConnection](CAPLfunctionAREthEstablishTCPConnection.md) function.

## Parameters

- **aepHandle**: Source application endpoint, which initiates the connection(s). Has to be defined in the database.
- **remotePort**: Port on which the messages can be both sent and received.
- **remoteIPv4Address**: IPv4 address to which the connection should be closed. IPv4 address can be converted with [IPGetAdressAsNumber](../../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsNumber.md).
- **remoteIPv6Address**: IPv6 address to which the connection should be closed. IPv6 address can be converted with [IpGetAddressAsArray](../../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsArray.md).
- **remoteIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the remote endpoint.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
variables
{
  dword aep; // application Endpoint handle
}

on start
{
  // handle has to have a valid database application endpoint description
  aep = AREthOpenLocalApplicationEndpoint IP_Endpoint(TCP:192.168.1.1:40000));
}

on key 'o'
{ 
  // opens connection to specific endpoint
  if (AREthEstablishTCPConnection(aep, IP_Endpoint(TCP:192.168.1.2:50000)) != 0)
  {
    write("connection not established");
  }
}

on key 'c'
{
  // close all connections within node context
  if (AREthCloseEstablishedTCPConnection () == 0)
  {
    write("connection(s) closed");
  }
}
```

[See Also](javascript:void(0);)
