# AREthSerializeMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AREthSerializeMessage(dword messageHandle, dword bufferLength, CHAR buffer[]); // form 1`
- `dword AREthSerializeMessage(dword messageHandle, dword bufferLength, BYTE buffer[]); // form 2`
- `dword AREthSerializeMessage(dword messageHandle, dword bufferLength, struct buffer[]); // form 3`

## Description

Serializes a SOME/IP message into a data buffer. Both the SOME/IP header and the payload are serialized.

**Note:** If the configuration of the SOME/IP message is invalid (e.g., incorrect value in length field or invalid content of payload), the message is **not** corrected when serialized. The message is passed unchanged.

## Parameters

- **messageHandle**: Handle of the message that was created with [AREthCreateMessage](CAPLfunctionAREthCreateMessage.md), for example.
- **bufferLength**: Length of the **buffer** parameter in bytes.
- **buffer**: Data buffer into which the SOME/IP message is serialized.

## Return Values

- **Number of copied bytes**: In the event of an error, the function returns the value 0. The [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```plaintext
on key 's'
{
  dword messageId = 0x12340004; // service ID = 0x1234, method ID = 0x0004
  dword requestId = 0;          // client ID = 0, session ID = 0
  dword protocolVersion = 1;
  dword interfaceVersion = 1;
  dword messageType = 0x2;      // notification message
  dword returnCode = 0;         // not available
  dword aep;                    // application endpoint handle
  dword messageHandle = 0;      // handle of the created SOME/IP message
  BYTE payload[5];              // the message payload
  dword count;                  // a simple counter
  BYTE buffer[21];              // serialization buffer

  // initialize the payload
  count = 0;
  payload[count++] = 0x11;
  payload[count++] = 0x22;
  payload[count++] = 0x33;
  payload[count++] = 0x44;
  payload[count++] = 0x55;

  // open application endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create the SOME/IP message itself
  messageHandle = AREthCreateMessage(messageId, requestId, protocolVersion, interfaceVersion, messageType, returnCode);

  // set message payload
  AREthSetData(messageHandle, elcount(payload), payload);

  // serialize message to data buffer
  AREthSerializeMessage(messageHandle, elcount(buffer), buffer);

  // The serialized message can now be added to a pure Ethernet packet using the function "EthSetTokenData".
}
```

**See Also**: [AREthGetData](CAPLfunctionAREthGetData.md), [AREthIsOptional](CAPLfunctionAREthIsOptional.md), [AREthSerializeMessage](#aanchor18598), [AREthSetData](CAPLfunctionAREthSetData.md), [SomeIpIsOptional](../../SOMEIPIL/Functions/CAPLfunctionSomeIpIsOptional.md)
