# SomeIpProvidedEventGroupAddConsumer

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long SomeIpProvidedEventGroupAddConsumer(dword pevgHandle, dword remoteIPv4Address, dword remoteUDPPort, dword remoteTCPPort); // form 1`
- `long SomeIpProvidedEventGroupAddConsumer(dword pevgHandle, byte remoteIPv6Address[], dword remoteUDPPort, dword remoteTCPPort); // form 2`
- `long SomeIpProvidedEventGroupAddConsumer(dword pevgHandle, IP_Endpoint remoteIPEndpoint); // form 3`

## Description

Adds a consumer to a provided event group. Afterwards event/field notifications will be sent to this consumer.

## Parameters

- **aepHandle**: An application endpoint.
- **pevgHandle**: Provided event group handle (may be retrieved by [SomeIpGetProvidedObjectHandle](CAPLfunctionSomeIpGetProvidedObjectHandle.md)).
- **remoteIPv4Address**: IPv4 address of the consumer. In network byte order.
- **remoteIPv6Address**: IPv6 address of the consumer.
- **remoteUDPPort**: An UDP port number of the consumer or zero if there is none.
- **remoteTCPPort**: A TCP port number of the consumer or zero if there is none.
- **remoteIPEndpoint**: Object of type IP_Endpoint that contains the address/port of the consumer.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

—
