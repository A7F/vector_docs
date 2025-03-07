[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpEstablishTCPConnection.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » SomeIpEstablishTCPConnection

# SomeIpEstablishTCPConnection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword SomeIpEstablishTCPConnection (); // form 1`
- `dword SomeIpEstablishTCPConnection (dword aepHandle); // form 2`
- `dword SomeIpEstablishTCPConnection (dword aepHandle, dword remoteIPv4Address); // form 3`
- `dword SomeIpEstablishTCPConnection (dword aepHandle, dword remoteIPv4Address, dword remotePort); // form 4`
- `dword SomeIpEstablishTCPConnection (dword aepHandle, byte remoteIPv6Address[]); // form 5`
- `long SomeIpEstablishTCPConnection (dword aepHandle, byte remoteIPv6Address[], dword remotePort); // form 6`
- `long SomeIpEstablishTCPConnection (dword aepHandle, IP_Endpoint remoteIPEndpoint); // form 7`

## Description

Establishes one or multiple database defined TCP connection(s).

- **Form 1**: Establishes all TCP connections of this node (as TCP client)
- **Form 2**: Establishes all TCP connections of TCP client
- **Form 3/5**: Establishes all TCP connections of TCP client to specific TCP server
- **Form 4/6**: Establishes TCP connection of TCP client to specific TCP server

A TCP connection can be closed using the [SomeIpCloseEstablishedTCPConnection](CAPLfunctionSomeIpCloseEstablishedTCPConnection.md) function.

## Parameters

- **aepHandle**: Source application endpoint, which initiates the connection(s). Has to be defined in the database.
- **remotePort**: Port on which the messages can be both sent and received.
- **remoteIPv4Address**: IPv4 address to which the connection should be established. IPv4 address can be converted with [IPGetAdressAsNumber](../../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsNumber.md).
- **remoteIPv6Address**: IPv6 address to which the connection should be established. IPv6 address can be converted with [IpGetAddressAsArray](../../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsArray.md).
- **remoteIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the remote endpoint.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../AUTOSARethIL/CAPLfunctionsAREthILErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)