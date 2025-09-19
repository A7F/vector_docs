[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetMessageType.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpGetMessageType**

# SomeIpGetMessageType

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpGetMessageType ( dword messageHandle );
```

## Description

This function returns the Message Type from the SOME/IP message header.

## Parameters

- **messageHandle**: Handle of the SOME/IP message (e.g. see [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md))

## Return Values

- **Message type**:
  - 0x00: REQUEST
  - 0x01: REQUEST_NO_RETURN
  - 0x02: NOTIFICATION
  - 0x40: REQUEST ACK
  - 0x41: REQUEST_NO_RETURN ACK
  - 0x42: NOTIFICATION ACK
  - 0x80: RESPONSE
  - 0x81: ERROR
  - 0xC0: RESPONSE ACK
  - 0xC1: ERROR ACK

In the event of an error, the function returns the value 0. The [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```plaintext
void OnSomeIpMessage( DWORD messageHandle )
{
  DWORD msgType       = 0;
  LONG  errorCode     = 0;
  LONG  errorOccured  = 0;

  // get data from SOME/IP message
  if((msgType = SomeIpGetMessageType(messageHandle)) == 0)
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
    write("SOME/IP message with Message Type 0x%02x received",msgType);
  } // if
}
```

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
