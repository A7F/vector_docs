[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpProvidedEventGroupRemoveConsumer.md)

## SomeIpProvidedEventGroupRemoveConsumer

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpProvidedEventGroupRemoveConsumer

### Tool Availability

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

- `long SomeIpProvidedEventGroupRemoveConsumer(dword pevgHandle, dword remoteIPv4Address, dword remoteUDPPort, dword remoteTCPPort); // form 1`
- `long SomeIpProvidedEventGroupRemoveConsumer(dword pevgHandle, byte remoteIPv6Address[], dword remoteUDPPort, dword remoteTCPPort); // form 2`
- `long SomeIpProvidedEventGroupRemoveConsumer(dword pevgHandle, IP_Endpoint remoteIPEndpoint); // form 3`

### Description

Removes a consumer from a provided event group. Afterwards event/field notifications will not be sent to this consumer anymore.

### Parameters

- **pevgHandle**: Provided event group handle (may be retrieved by [SomeIpGetProvidedObjectHandle](CAPLfunctionSomeIpGetProvidedObjectHandle.md)).
- **remoteIPv4Address**: IPv4 address of the consumer. In network byte order.
- **remoteIPv6Address**: IPv6 address of the consumer.
- **remoteUDPPort**: An UDP port number of the consumer or zero if there is none.
- **remoteTCPPort**: A TCP port number of the consumer or zero if there is none.
- **remoteIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the consumer.

### Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)