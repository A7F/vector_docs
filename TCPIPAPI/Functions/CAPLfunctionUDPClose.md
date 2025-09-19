[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionUDPClose.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » UdpClose

# UdpClose

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long UdpClose( dword socket);
```

## Method Syntax as [Destructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
ssocket.Close()
```

## Description

The function closes the UDP socket. Upon successful completion the passed socket is no longer valid.

## Parameters

- **socket**: The socket to be closed.

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

## Example

See example [Create UDP Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md#UDPServerSocket).

[UdpOpen](CAPLfunctionUDPOpen.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
