# OnTlsEarlyDataReceived

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void OnTlsEarlyDataReceived(dword socket, char buffer[], dword size);
```

## Description

To handle early data from the TLS 1.3 client, the CAPL server program must implement this callback. It is called with the decrypted early data when early data is received and accepted during a TLS 1.3 handshake.

To enable the server to send data to the unauthenticated client, before the handshake is completed, one should set the TCP_NODELAY option on the corresponding socket to 1, to disable Nagle’s algorithm (see code example). It can be reactivated after the handshake, e.g. within the [OnTlsHandshakeComplete](CAPLfunctionOnTlsHandshakeComplete.md) callback. As an alternative to the CAPL code, one can disable **Tcp Delayed Acknowledge activated** in the TCP/IP Stack settings.

## Parameters

- **socket**: The TLS socket handle.
- **buffer**: The buffer containing the received decrypted early data.
- **size**: The size of the received data.

## Return Values

—

## Example

```plaintext
variables
{
  CHAR gReceiveBuffer[2000];
}

void OnTlsEarlyDataReceived(dword socket, char buffer[], dword size)
{
  const dword replySize = 17;
  CHAR earlyDataReply[replySize] = "Early data reply";
  //
  // Do something useful with the data...
  //

  // Allows the server to directly send data to the unauthenticated client
  ipSetSocketOption(socket, "IPPROTO_TCP", "TCP_NODELAY", 1);

  TcpSend(socket, earlyDataReply, replySize);

  // continue receiving data on the socket
  TcpReceive(socket, gReceiveBuffer, elcount(gReceiveBuffer) );
}

void OnTlsHandshakeComplete(dword socket, int result)
{
  ipSetSocketOption(socket, "IPPROTO_TCP", "TCP_NODELAY", 0);
}
```

[**tlsAuthenticateAsClientWithConfigurationAndEarlyData**](../Functions/CAPLFunctiontlsAuthenticateAsClientWithConfigurationAndEarlyData.md) • [**HasEarlyDataBeenAccepted**](../Functions/CAPLFunctionHasEarlyDataBeenAccepted.md)
