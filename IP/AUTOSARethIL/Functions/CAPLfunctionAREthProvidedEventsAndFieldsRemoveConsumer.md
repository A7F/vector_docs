# AREthProvidedEventsAndFieldsRemoveConsumer

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long AREthProvidedEventsAndFieldsRemoveConsumer(dword psiHandle, dword remoteIPv4Address, dword remoteUDPPort, dword remoteTCPPort); // form 1`
- `long AREthProvidedEventsAndFieldsRemoveConsumer(dword psiHandle, byte remoteIPv6Address[], dword remoteUDPPort, dword remoteTCPPort); // form 2`
- `long AREthProvidedEventsAndFieldsRemoveConsumer(dword psiHandle, IP_Endpoint remoteIPEndpoint); // form 3`

## Description

Removes a consumer from a provided service instance that has been added by [AREthProvidedEventsAndFieldsAddConsumer](CAPLfunctionAREthProvidedEventsAndFieldsAddConsumer.md).

## Parameters

- **psiHandle**: Provided service instance handle (may be retrieved by [AREthGetProvidedObjectHandle](CAPLfunctionAREthGetProvidedObjectHandle.md)).
- **remoteIPv4Address**: IPv4 address of the consumer. In network byte order.
- **remoteIPv6Address**: IPv6 address of the consumer.
- **remoteUDPPort**: An UDP port number of the consumer or zero if there is none.
- **remoteTCPPort**: A TCP port number of the consumer or zero if there is none.
- **remoteIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the consumer.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

—
