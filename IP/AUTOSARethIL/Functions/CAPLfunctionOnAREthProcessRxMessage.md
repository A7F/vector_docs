[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthProcessRxMessage.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **OnAREthProcessRxMessage**

# OnAREthProcessRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long OnAREthProcessRxMessage(dword messageHandle, long rxChannel);
```

## Description

This callback function is called whenever the IL has received a SOME/IP message.

The return value of this callback determines if the message should be processed by the IL or if it should be ignored. Furthermore, the message may be modified before the IL processes the message.

## Parameters

- **messageHandle**: Handle of the received SOME/IP message that triggered the callback.
- **rxChannel**: The channel of the application endpoint that received the message.

## Return Values

The message will be processed if the callback returns 1.

Otherwise, the message has been ignored by the callback.

## Example

```plaintext
long OnAREthProcessRxMessage(dword messageHandle, long rxChannel)
{
  DWORD msgId = 0;
  LONG errorCode = 0;
  LONG errorOccured = 0;
  // get data from SOME/IP message
  if((msgId = AREthGetMessageId(messageHandle)) == 0)
  {
    // check if last function was executed correct
    if((errorCode = AREthGetLastError()) != 0)
    {
      write("SOME/IP IL error occured: Error code: %d", errorCode);
      errorOccured = 1;
    } // if
  } // if
  if(errorOccured == 0)
  {
    write("SOME/IP message with Message ID 0x%08x received",msgId);
    return 1;
  } // if
  else
  {
    return 0;
  } // else
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)