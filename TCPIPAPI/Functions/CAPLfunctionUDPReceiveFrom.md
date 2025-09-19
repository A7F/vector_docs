[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionUDPReceiveFrom.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » UdpReceiveFrom

# UdpReceiveFrom

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long UdpReceiveFrom( dword socket, char buffer[], dword size);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
socket.ReceiveFrom( char buffer[], dword size);
```

## Description

The function receives data into the specified buffer. If the receive operation does not complete immediately the operation is performed asynchronously and the function will return SOCKET_ERROR (-1). Use [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code. If the specific error code is WSA_IO_PENDING (997) the CAPL callback [OnUdpReceiveFrom](../EventProcedures/CAPLfunctionTCPIPOnUdpReceiveFrom.md) will be called on completion (successful or not), provided it is implemented in the same CAPL program.

## Parameters

- **socket**: The socket handle.
- **buffer**: The buffer used to store the incoming data.
- **size**: The size of the data buffer.

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code.

## Example

See example [Create UDP Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md#UDPServerSocket).

[UdpOpen](CAPLfunctionUDPOpen.md) • [UdpClose](CAPLfunctionUDPClose.md) • [UdpSendTo](CAPLfunctionUDPSendTo.md) • [OnUdpReceiveFrom](../EventProcedures/CAPLfunctionTCPIPOnUdpReceiveFrom.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
