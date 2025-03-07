[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSetMulticastReceiverEndpoints.md)

# AREthSetMulticastReceiverEndpoints

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthSetMulticastReceiverEndpoints

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long AREthSetMulticastReceiverEndpoints(dword cevgHandle, dword multicastIPv4Address, dword udpPort)` // form 1
- `long AREthSetMulticastReceiverEndpoints(dword cevgHandle, byte multicastIPv6Address[], dword udpPort)` // form 2
- `long AREthSetMulticastReceiverEndpoints(dword cevgHandle, IP_Endpoint multicastIPEndpoint);` // form 3

## Description

Sets the multicast endpoint that is used for the consumed event group to receive field/event notification per multicast.

## Parameters

- **cevgHandle**: Consumed event group handle (may be retrieved by [AREthGetConsumedObjectHandle](CAPLfunctionAREthGetConsumedObjectHandle.md)).
- **multicastIPv4Address**: Multicast IPv4 address receiving the events/fields. In network byte order.
- **multicastIPv6Address**: Multicast IPv6 address receiving the events/fields.
- **udpPort**: An UDP port number receiving the events/fields. May be zero if the events/fields shall not be received by multicast anymore.
- **multicastIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the multicast endpoint. An **IP_Endpoint** with port number zero may be passed to delete a previously set **IP_Endpoint**.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)