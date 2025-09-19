[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthProvidedFieldRemoveConsumer.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » AREthProvidedFieldRemoveConsumer

# AREthProvidedFieldRemoveConsumer

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

- `long AREthProvidedFieldRemoveConsumer(dword pfHandle, dword remoteIPv4Address, dword remoteUDPPort, dword remoteTCPPort);` // form 1
- `long AREthProvidedFieldRemoveConsumer(dword pfHandle, byte remoteIPv6Address[], dword remoteUDPPort, dword remoteTCPPort);` // form 2
- `long AREthProvidedFieldRemoveConsumer(dword pfHandle, IP_Endpoint remoteIPEndpoint);` // form 3

## Description

Removes a consumer from a provided field that has been added by [AREthProvidedFieldAddConsumer](CAPLfunctionAREthProvidedFieldAddConsumer.md).

## Parameters

- **pfHandle**: Provided field handle (may be retrieved by [AREthGetProvidedObjectHandle](CAPLfunctionAREthGetProvidedObjectHandle.md)).
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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
