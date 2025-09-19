[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpOutputMessage.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpOutputMessage**

# SomeIpOutputMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpOutputMessage( dword aepHandle, dword remoteIPv4Address, dword remotePort, dword messageHandle ); // form 1
long SomeIpOutputMessage( dword aepHandle, IP_Endpoint remoteIPEndpoint, dword messageHandle); // form 2
```

## Description

This function is used to send a SOME/IP message.

The packet is sent immediately. All messages that were prepared for sending beforehand with [SomeIpPostMessage](CAPLfunctionSomeIpPostMessage.md) are inserted in the packet to be sent and sent with the message, provided that the buffered messages have the same source and the same destination.

## Parameters

- **aepHandle**: Handle of the local Application Endpoint over which the message should be output.
- **remoteIPv4Address**: IPv4 address to which the message should be sent (Network Byte Order).
- **remotePort**: UDP/TCP port number to which the message should be sent.
- **remoteIPEndpoint**: Object of type IP_Endpoint that contains the address/port of the remote endpoint.
- **messageHandle**: Handle of the message that was created with SomeIpCreateMessage, for example.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key 's'
{
  DWORD messageId = 0x12340004; // service ID = 0x1234, method ID = 0x0004
  DWORD requestId = 0; // client ID = 0, session ID = 0
  DWORD protocolVersion = 1;
  DWORD interfaceVersion = 1;
  DWORD messageType = 0x2; // notification message
  DWORD returnCode = 0; // not available
  DWORD aep = 0; // application endpoint handle
  DWORD messageHandle = 0; // handle of the created SOME/IP message
  BYTE payload[5]; // the message payload
  DWORD count = 0; // a simple counter

  // initialize the payload
  count = 0;
  payload[count++] = 0x11;
  payload[count++] = 0x22;
  payload[count++] = 0x33;
  payload[count++] = 0x44;
  payload[count++] = 0x55;

  // open application endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create the SOME/IP message itself and set the message payload
  messageHandle = SomeIpCreateMessage(messageId,requestId,protocolVersion,interfaceVersion,messageType,returnCode);
  SomeIpSetData(messageHandle,elcount(payload),payload);

  // send the SOME/IP message
  SomeIpOutputMessage(aep,0xFFFFFFFF,40001,messageHandle);

  // release the some IP message
  SomeIpReleaseMessage(messageHandle);
}
```

[See Also](javascript:void(0);)

```markdown
