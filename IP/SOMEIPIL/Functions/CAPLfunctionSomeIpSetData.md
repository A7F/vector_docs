[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpSetData.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpSetData

# SomeIpSetData

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpSetData(dword messageHandle, dword dataLength, char data[]);
long SomeIpSetData(dword messageHandle, dword dataLength, byte data[]);
long SomeIpSetData(dword messageHandle, dword dataLength, struct data);
```

## Description

This function can be used to set the payload of a SOME/IP message. If data in the payload of the message already exist, the data will be overwritten with this function call.

If necessary the length field in the SOME/IP Message Header will be adapted at the function call.

## Parameters

- **messageHandle**: Handle of the received SOME/IP message (see [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md))
- **dataLength**: Number of data bytes
- **data**: Data that should be copied to the SOME/IP message

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
