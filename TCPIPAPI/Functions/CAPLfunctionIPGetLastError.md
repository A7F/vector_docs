[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetLastError.md)

# IpGetLastError

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetLastError

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetLastError();
```

## Description

The function returns the [Winsock 2 error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md) of the last operation that failed.

## Parameters

—

## Return Values

The error code as provided by the Winsock 2 WSAGetLastError function.

## Example

```plaintext
on start
{
  // produces an error 10049...
  TcpOpen(0xffffffff, 1);

  writeLineEx(1, 3, "IpGetLastError: %d", IpGetLastError());
}
```
