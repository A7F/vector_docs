[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpProvidedEventRemoveConsumer.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpProvidedEventRemoveConsumer

# SomeIpProvidedEventRemoveConsumer

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpProvidedEventRemoveConsumer(dword pevHandle, dword remoteIPv4Address, dword remoteUDPPort, dword remoteTCPPort); // form 1
long SomeIpProvidedEventRemoveConsumer(dword pevHandle, byte remoteIPv6Address[], dword remoteUDPPort, dword remoteTCPPort); // form 2
long SomeIpProvidedEventRemoveConsumer(dword pevHandle, IP_Endpoint removeIPEndpoint); // form 3
```

## Description

Removes a consumer from a provided event that has been added by [SomeIpProvidedEventAddConsumer](CAPLfunctionSomeIpProvidedEventAddConsumer.md).

## Parameters

- **pevHandle**: Provided event handle (may be retrieved by [SomeIpGetProvidedObjectHandle](CAPLfunctionSomeIpGetProvidedObjectHandle.md))
- **remoteIPv4Address**: IPv4 address of the consumer. In network byte order.
- **remoteIPv6Address**: IPv6 address of the consumer
- **remoteUDPPort**: An UDP port number of the consumer or zero if there is none
- **remoteTCPPort**: A TCP port number of the consumer or zero if there is none
- **remoteIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the consumer.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
