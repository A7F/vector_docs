[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpSerializeMessage.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpSerializeMessage**

# SomeIpSerializeMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpSerializeMessage(dword messageHandle, dword bufferLength, CHAR buffer[]);
dword SomeIpSerializeMessage(dword messageHandle, dword bufferLength, BYTE buffer[]);
dword SomeIpSerializeMessage(dword messageHandle, dword bufferLength, struct buffer[]);
```

## Description

Serializes a SOME/IP message into a data buffer. Both the SOME/IP header and the payload are serialized.

**Note**: If the configuration of the SOME/IP message is invalid (for example, incorrect value in length field or invalid content of payload), the message is **not** corrected when serialized. The message is passed unchanged.

## Parameters

- **messageHandle**: Handle of the message that was created with [SomeIpCreateMessage](CAPLfunctionSomeIpCreateMessage.md), for example.
- **bufferLength**: Length of the **buffer** parameter in bytes.
- **buffer**: Data buffer into which the SOME/IP message is serialized.

## Return Values

- **Number of copied bytes**: In the event of an error, the function returns the value 0. The [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```plaintext
on key 's'
{
  DWORD messageId = 0x12340004; // service ID = 0x1234, method ID = 0x0004
  DWORD requestId = 0;          // client ID = 0, session ID = 0
  DWORD protocolVersion = 1;
  DWORD interfaceVersion = 1;
  DWORD messageType = 0x2;      // notification message
  DWORD returnCode = 0;         // not available
  DWORD aep;                    // application endpoint handle
  DWORD messageHandle = 0;      // handle of the created SOME/IP message
  BYTE payload[5];              // the message payload
  DWORD count;                  // a simple counter
  BYTE buffer[21];              // serialization buffer

  // initialize the payload
  count = 0;
  payload[count++] = 0x11;
  payload[count++] = 0x22;
  payload[count++] = 0x33;
  payload[count++] = 0x44;
  payload[count++] = 0x55;

  // open application endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create the SOME/IP message itself
  messageHandle = SomeIpCreateMessage(messageId,requestId,protocolVersion,interfaceVersion,messageType,returnCode);

  // set message payload
  SomeIpSetData(messageHandle,elcount(payload),payload);

  // serialize message to data buffer
  SomeIpSerializeMessage(messageHandle,elcount(buffer),buffer);

  // The serialized message can now be added to a pure Ethernet packet using the function "EthSetTokenData".
}
```

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
