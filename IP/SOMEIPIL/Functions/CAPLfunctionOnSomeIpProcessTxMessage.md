[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionOnSomeIpProcessTxMessage.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **OnSomeIpProcessTxMessage**

# OnSomeIpProcessTxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long OnSomeIpProcessTxMessage(dword messageHandle, long txChannel);
```

## Description

This callback function is called whenever the IL wants to send a SOME/IP message.

The return value of this callback determines if the message should be sent or if it should be blocked. Furthermore, the message may be modified before the IL sends the message.

## Parameters

- **messageHandle**: Handle of the to be sent message that triggered the callback.
- **txChannel**: The channel of the application endpoint that will be used to send the message.

## Return Values

The message will be sent if the callback returns 1. Otherwise, the message has been filtered by the callback.

## Example

```plaintext
long OnSomeIpProcessTxMessage(dword messageHandle, long txChannel)
{
  DWORD msgId = 0;
  LONG errorCode = 0;
  LONG errorOccured = 0;
  // get data from SOME/IP message
  if((msgId = SomeIpGetMessageId(messageHandle)) == 0)
  {
    // check if last function was executed correct
    if((errorCode = SomeIpGetLastError()) != 0)
    {
      write("SOME/IP IL error occured: Error code: %d", errorCode);
      errorOccured = 1;
    } // if
  } // if
  if(errorOccured == 0)
  {
    write("SOME/IP message with Message ID 0x%08x is send",msgId);
    return 1;
  } // if
  else
  {
    return 0;
  } // else
}
```

[See Also](javascript:void(0);)
