[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/CAPLfunctionsTCPIPTechnicalDetails.md)

## CAPL Functions » TCP/IP API » Technical Details

### Socket Handles

Except for the network information functions of the IP API most of the CAPL Socket API functions take a socket handle of type `dword` as a first parameter.

**Note**  
This handle parameter is not the underlying WIN32 SOCKET handle and thus of no general use. You should treat this parameter as an opaque handle.

### Socket Behavior

All sockets are created as overlapped sockets and are operated in non-blocking mode. All functions, which cannot complete immediately, are performed in an overlapped and asynchronous manner. Upon completion (successful or not) the CAPL program receives a callback provided that it implements the required completion routine.

### Error Handling

Almost all of the functions have a return value of type `long`. The value returned indicates the status of the operation (successful or not) and is – in almost all cases - identical to the return value of the underlying Winsock 2 API. That means that the return value is typically either zero if no error occurs or SOCKET_ERROR (-1) otherwise. To get a specific error code for the last socket operation, use the [IpGetLastSocketError](Functions/CAPLfunctionIPGetLastSocketError.md) function. If an invalid socket handle is passed to a CAPL Socket API function the value WSA_INVALID_PARAMETER (87) is returned.

**Note**  
Because the entire Winsock 2 API is used in an overlapped, asynchronous manner, functions such as [UdpReceiveFrom](Functions/CAPLfunctionUDPReceiveFrom.md), [TcpReceive](Functions/CAPLfunctionTCPReceive.md) and [TcpConnect](Functions/CAPLfunctionTCPConnect.md) will almost always return the value SOCKET_ERROR. Use the [IpGetLastSocketError](Functions/CAPLfunctionIPGetLastSocketError.md) function to determine whether the operation is just pending or a real error has occurred.

[Winsock 2 Error Codes](CAPLfunctionsTCPIPWinsock2ErrorCodes.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)