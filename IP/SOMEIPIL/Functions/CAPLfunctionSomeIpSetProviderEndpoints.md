[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpSetProviderEndpoints.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpSetProviderEndpoints

# SomeIpSetProviderEndpoints

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long SomeIpSetProviderEndpoints(dword csiHandle, dword remoteIPv4Address, dword remoteUDPPort, dword remoteTCPPort); // form 1`
- `long SomeIpSetProviderEndpoints(dword csiHandle, byte remoteIPv6Address[], dword remoteUDPPort, dword remoteTCPPort); // form 2`
- `long SomeIpSetProviderEndpoints(dword csiHandle, IP_Endpoint remoteIPEndpoint); // form 3`

## Description

Sets the UDP and TCP endpoint that is used for the consumed service instance to reach the corresponding provided service instance.

## Parameters

- **csiHandle**: Consumed service instance handle (may be retrieved by [SomeIpGetConsumedObjectHandle](CAPLfunctionSomeIpGetConsumedObjectHandle.md)).
- **remoteIPv4Address**: IPv4 address of the provider. In network byte order.
- **remoteIPv6Address**: IPv6 address of the provider.
- **remoteUDPPort**: An UDP port number of the provider or zero if there is none.
- **remoteTCPPort**: A TCP port number of the provider or zero if there is none.
- **remoteIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the provider. An **IP_Endpoint** with port number zero may be passed to delete a previously set **IP_Endpoint**.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
