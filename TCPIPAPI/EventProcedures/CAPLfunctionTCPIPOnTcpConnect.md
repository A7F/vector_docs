[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnTcpConnect.md)

**CAPL Functions** » **TCP/IP API** » **OnTcpConnect**

# OnTcpConnect

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnTcpConnect( dword socket, long result);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
void OnTcpConnect( TcpSocket socket, long result);
```

## Description

If the CAPL program implements this callback it is called when an asynchronous connection operation completes. This means that the connection to the remote station has been established. It is not yet certain at this time that the remote station has accepted the connection with [TcpAccept](../Functions/CAPLfunctionTCPAccept.md).

If a listen socket of a remote station is blocked, error 10061 (Connection refused) is output in the **result** parameter.

## Parameters

- **socket**: The socket handle or socket object.
- **result**: The specific result code of the operation. If the operation completed successfully the value is 0. Otherwise the value is an [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md).

  **Error code 10061 (Connection refused):** The listen socket of a server is occupied by another connection that has not yet been accepted with [TcpAccept](../Functions/CAPLfunctionTCPAccept.md). Because the internal queue for incoming connections is set to 1 in the CANoe DE product, only one node can ever queue up there. All other nodes are refused with error 10061.

## Return Values

—

## Example

```plaintext
// ---------------------------------------------------
// connect a client and return the socket handle
// ---------------------------------------------------
dword clientConnect(dword targetIP, dword port)
{
  dword resultSocket;
  resultSocket = TcpOpen (0,0);
  if (resultSocket != ~0)
  {
    TcpConnect ( resultSocket, targetIP, port );
    // => Connection established in callback OnTcpConnect...
  }
  else
  {
    writeLineEx(1, 3, " [ TcpOpen: FAILED. ]");
  }
  return resultSocket;
}

// ---------------------------------------------------
// Connection operation completes
// ---------------------------------------------------
void OnTcpConnect( dword socket, long result)
{
  if (result == 0)
  {
    // start receiving on socket using TcpReceive …
  }
  else
  {
    writeLineEx(1, 3, "OnTcpConnect error %d", result);
  }
}
```

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)