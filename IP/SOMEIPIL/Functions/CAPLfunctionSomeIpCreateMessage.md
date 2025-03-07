[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpCreateMessage.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpCreateMessage**

# SomeIpCreateMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword SomeIpCreateMessage( dword messageId, dword requestId, dword protocolVersion, dword interfaceVersion, dword messageType, dword returnCode ); // form 1`
- `dword SomeIpCreateMessage( dword bufferLength, byte buffer[] ); // form 2`
- `dword SomeIpCreateMessage( dword bufferLength, byte buffer[], dword offset ); // form 3`

## Description

This function is used to create a SOME/IP message that can then be sent with [SomeIpOutputMessage](CAPLfunctionSomeIpOutputMessage.md) or [SomeIpPostMessage](CAPLfunctionSomeIpPostMessage.md).

**Form 1**  
If a FIBEX database is assigned to the CANoe configuration, a check is made to determine whether the message ID (`messageId` parameter) is contained in this database. If so, the payload is created according to the database description and initialized with 0. The length field in the SOME/IP message header is set automatically. If a corresponding message ID is not found in the database, only the SOME/IP message header is created. In this case, the payload must be created with [SomeIpSetData](CAPLfunctionSomeIpSetData.md). If no payload is available an empty payload must be specified in [SomeIpSetData](CAPLfunctionSomeIpSetData.md).

**Form 2**  
During creation, the message header length is taken from the data stream specified in the `buffer` parameter. In so doing, incorrect length values are not corrected.

If the message is successfully accessed later with a [SomeIpGetValue...](CAPLfunctionSomeIpGetValue.md) or [SomeIpSetValue...](CAPLfunctionSomeIpSetValue.md) function, the length is adapted in the message, if necessary, if a FIBEX database is assigned to the CANoe configuration and the message ID is contained in the database.

The created message can be deleted again with [SomeIpReleaseMessage](CAPLfunctionSomeIpReleaseMessage.md).

## Parameters

- **messageId**: The message identifier of the SOME/IP message.
- **requestId**: The request identifier of the SOME/IP message header.
- **protocolVersion**: The protocol version of the SOME/IP message header.
- **interfaceVersion**: The interface version of the SOME/IP message header.
- **messageType**: The message type of the SOME/IP message header.
- **returnCode**: The return code of the SOME/IP message header.
- **bufferLength**: Length of the buffer parameter in bytes.
- **buffer**: Buffer that contains the complete SOME/IP message as byte stream.
- **offset**: This parameter can be used to specify the start of a SOME/IP message in the byte stream. The specification is in bytes (see example code).

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
- **>0**: Handle of the created message

## Example

```c
on key 's'
{
  DWORD messageId = 0x12340004; // service ID = 0x1234, method ID = 0x0004
  DWORD requestId = 0; // client ID = 0, session ID = 0
  DWORD protocolVersion = 1;
  DWORD interfaceVersion = 1;
  DWORD messageType = 0x2; // notification message
  DWORD returnCode = 0; // not available
  DWORD aep = 0;          // application endpoint handle
  DWORD messageHandle    = 0; // handle of the created SOME/IP message
  BYTE payload[5]; // the message payload
  DWORD count            = 0; // a simple counter

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