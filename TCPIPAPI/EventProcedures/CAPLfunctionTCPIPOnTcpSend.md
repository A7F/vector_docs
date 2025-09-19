[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnTcpSend.md)

**CAPL Functions** » **TCP/IP API** » **OnTcpSend**

# OnTcpSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnTcpSend( dword socket, long result, char buffer[], dword size);
```

## Method Syntax

```plaintext
void OnTcpSend( TcpSocket socket, long result, char buffer[], dword size);
```

## Description

If the CAPL program implements this callback it is called when the data from the stack have been processed but not yet placed on the bus. The information is first displayed in the CANoe DE product Trace Window when it has physically been sent.

## Parameters

- **socket**: The socket handle or socket object.
- **result**: The result code of the asynchronous operation. If the operation completed successfully the value is 0. Otherwise the value is an [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md).
- **buffer**: The buffer provided with the send operation.
- **size**: The number of bytes sent.

## Return Values

—

## Example

```plaintext
// ---------------------------------------------------
// When asynchronous TcpSend is complete...
// ---------------------------------------------------
void OnTcpSend( dword socket, long result, char buffer[], dword size)
{
  if (socket != ~0)
  {
    // sending data complete.
    If (result != 0)
    {
      writeLineEx(1, 3, "OnTcpSend error: %d", result);
    }
  }
}
```

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
