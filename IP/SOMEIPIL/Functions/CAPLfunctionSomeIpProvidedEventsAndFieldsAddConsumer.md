[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpProvidedEventsAndFieldsAddConsumer.md)

## SomeIpProvidedEventsAndFieldsAddConsumer

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpProvidedEventsAndFieldsAddConsumer

### Tool Availability
[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Function Syntax

- `long SomeIpProvidedEventsAndFieldsAddConsumer(dword psiHandle, dword remoteIPv4Address, dword remoteUDPPort, dword remoteTCPPort); // form 1`
- `long SomeIpProvidedEventsAndFieldsAddConsumer(dword psiHandle, byte remoteIPv6Address[], dword remoteUDPPort, dword remoteTCPPort); // form 2`
- `long SomeIpProvidedEventsAndFieldsAddConsumer(dword psiHandle, IP_Endpoint remoteIPEndpoint); // form 3`

### Description

Adds a consumer to a provided service instance. Afterwards all event/field notifications belonging to this service instance will be sent to this consumer.

### Parameters

- **psiHandle**: Provided service instance handle (may be retrieved by [SomeIpGetProvidedObjectHandle](CAPLfunctionSomeIpGetProvidedObjectHandle.md)).
- **remoteIPv4Address**: IPv4 address of the consumer. In network byte order.
- **remoteIPv6Address**: IPv6 address of the consumer.
- **remoteUDPPort**: An UDP port number of the consumer or zero if there is none.
- **remoteTCPPort**: A TCP port number of the consumer or zero if there is none.
- **remoteIPEndpoint**: Object of type `IP_Endpoint` that contains the address/port of the consumer.

### Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

### Example

—
