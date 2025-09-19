[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSetRequestId.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthSetRequestId**

# AREthSetRequestId

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
LONG AREthSetRequestId(dword messageHandle, dword requestId);
```

## Description

This function sets the request ID in the SOME/IP message header.

## Parameters

- **messageHandle**: Handle of the SOME/IP message (e.g. see [OnAREthMessage](CAPLfunctionOnAREthMessage.md))
- **requestId**: New request ID

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on key 's'
{
  dword messageId        = 0x12340004; // service ID = 0x1234, method ID = 0x0004
  dword requestId        = 0;          // client ID = 0, session ID = 0
  dword protocolVersion  = 1;
  dword interfaceVersion = 1;
  dword messageType      = 0x2;        // notification message
  dword returnCode       = 0;          // not available
  dword aep              = 0;          // application endpoint handle
  dword messageHandle    = 0;          // handle of the created SOME/IP message
  BYTE payload[5];                     // the message payload
  dword count            = 0;          // a simple counter

  // initialize the payload
  count = 0;
  payload[count++] = 0x11;
  payload[count++] = 0x22;
  payload[count++] = 0x33;
  payload[count++] = 0x44;
  payload[count++] = 0x55;

  // open application endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create the SOME/IP message itself and set the message payload
  messageHandle = AREthCreateMessage(messageId, requestId, protocolVersion, interfaceVersion, messageType, returnCode);
  AREthSetData(messageHandle, elcount(payload), payload);

  // send five SOME/IP message using different Request IDs
  for(count = 0; count < 5; count++)
  {
    AREthSetRequestId(messageHandle, count);
    AREthOutputMessage(aep, 0xFFFFFFFF, 40001, messageHandle);
  } // for

  // release the some IP message
  AREthReleaseMessage(messageHandle);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
