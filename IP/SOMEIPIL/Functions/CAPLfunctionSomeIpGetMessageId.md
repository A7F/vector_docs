[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetMessageId.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpGetMessageId**

# SomeIpGetMessageId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword SomeIpGetMessageId ( dword messageHandle );
```

## Description

This function returns the Message ID from the SOME/IP message header.

## Parameters

- **messageHandle**: Handle of the SOME/IP message (e.g. see [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md))

## Return Values

- **SOME/IO message ID**: In the event of an error, the function returns the value 0. The [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```c
void OnSomeIpMessage( DWORD messageHandle )
{
  DWORD msgId        = 0;
  LONG  errorCode    = 0;
  LONG  errorOccured = 0;

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
    write("SOME/IP message with Message ID 0x%08x received",msgId);
  } // if
}
```

[See Also](javascript:void(0);)