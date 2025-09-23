# AREthSendARPDUTo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long AREthSendARPDUTo( dword aep, dword dstIPv4Addr, dword dstPort, dword bufferLength, char buffer[], dword headerID ); // form 1`
- `long AREthSendARPDUTo( dword aep, dword dstIPv4Addr, dword dstPort, dword bufferLength, byte buffer[], dword headerID ); // form 2`
- `long AREthSendARPDUTo( dword aep, dword dstIPv4Addr, dword dstPort, dword bufferLength, struct buffer, dword headerID ); // form 3`
- `long AREthSendARPDUTo( dword aep, byte dstIPv6Addr[], dword dstPort, dword bufferLength, char buffer[], dword headerID ); // form 4`
- `long AREthSendARPDUTo( dword aep, byte dstIPv6Addr[], dword dstPort, dword bufferLength, byte buffer[], dword headerID ); // form 5`
- `long AREthSendARPDUTo( dword aep, byte dstIPv6Addr[], dword dstPort, dword bufferLength, struct buffer, dword headerID ); // form 6`
- `long AREthSendARPDUTo( dword aep, IP_Endpoint dstIPEndpoint, dword bufferLength, char buffer[], dword headerID ); // form 7`
- `long AREthSendARPDUTo( dword aep, IP_Endpoint dstIPEndpoint, dword bufferLength, byte buffer[], dword headerID ); // form 8`
- `long AREthSendARPDUTo( dword aep, IP_Endpoint dstIPEndpoint, dword bufferLength, struct buffer, dword headerID ); // form 9`

## Description

Transmits data as AUTOSAR PDU via an Ethernet connection with activated **Header** option. Before transmitting, each AUTOSAR PDU gets a Header that contains an ID and length.

## Parameters

- **aep**: Handle of an application endpoint that was opened with [AREthOpenLocalApplicationEndpoint](CAPLfunctionAREthOpenLocalApplicationEndpoint.md).
- **dstIPv4Addr**: IPv4 address of the target as dword, e.g. converted with [ipGetAddressAsNumber](../../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsNumber.md).
- **dstIPv6Addr**: IPv6 address of the target as byte array, e.g. converted with [ipGetAddressAsArray](../../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsArray.md).
- **dstPort**: UDP or TCP port of the target.
- **dstIPEndpoint**: Object of type **IP_Endpoint** that contains the address/port of the target.
- **bufferLength**: Buffer length of the data. The length is written in the preceded header during transmission.
- **buffer**: Data to transmit without header.
- **headerId**: ID which is to be written in the header.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)
