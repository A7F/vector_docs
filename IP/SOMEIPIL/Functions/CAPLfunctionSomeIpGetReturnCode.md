[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetReturnCode.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » SomeIpGetReturnCode

# SomeIpGetReturnCode

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword SomeIpGetReturnCode ( dword messageHandle );
```

## Description

This function returns the Return Code from the SOME/IP message header.

## Parameters

- **messageHandle**: Handle of the SOME/IP message (e.g. see [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md))

## Return Values

- **Return code**:
  - 0x00: E_OK
  - 0x01: E_NOT_OK
  - 0x02: E_UNKNOWN_SERVICE
  - 0x03: E_UNKNOWN_METHOD
  - 0x04: E_NOT_READY
  - 0x05: E_NOT_REACHABLE
  - 0x06: E_TIMEOUT
  - 0x07: E_WRONG_PROTOCOL_VERSION
  - 0x08: E_WRONG_INTERFACE_VERSION
  - 0x09: E_MALFORMED_MESSAGE
  - 0x09: 0x1F RESERVED

If message type is REQUEST, REQUEST_NO_RETURN or NOTIFICATION return code is N/A and set to 0x00 (E_OK).

In the event of an error, the function returns the value 0. The [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```c
void OnSomeIpMessage( DWORD messageHandle )
{
  DWORD retCode       = 0;
  LONG  errorCode     = 0;
  LONG  errorOccured  = 0;

  // get data from SOME/IP message
  if((retCode = SomeIpGetReturnCode(messageHandle)) == 0)
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
    write("SOME/IP message with Return Code 0x%02x received",retCode);
  } // if
}
```

[See Also](javascript:void(0);)
- [SomeIpFillValues](CAPLfunctionSomeIpFillValues.md)
- [SomeIpGetDestinationAddress](CAPLfunctionSomeIpGetDestinationAddress.md)
- [SomeIpGetDestinationPort](CAPLfunctionSomeIpGetDestinationPort.md)
- [SomeIpGetInterfaceVersion](CAPLfunctionSomeIpGetInterfaceVersion.md)
- [SomeIpGetLength](CAPLfunctionSomeIpGetLength.md)
- [SomeIpGetMessageId](CAPLfunctionSomeIpGetMessageId.md)
- [SomeIpGetMessageType](CAPLfunctionSomeIpGetMessageType.md)
- [SomeIpGetProtocol](CAPLfunctionSomeIpGetProtocol.md)
- [SomeIpGetProtocolVersion](CAPLfunctionSomeIpGetProtocolVersion.md)
- [SomeIpGetRequestId](CAPLfunctionSomeIpGetRequestId.md)
- [SomeIpGetReturnCode](#aanchor62)
- [SomeIpGetSourceAddress](CAPLfunctionSomeIpGetSourceAddress.md)
- [SomeIpGetSourcePort](CAPLfunctionSomeIpGetSourcePort.md)
- [SomeIpGetValue...](CAPLfunctionSomeIpGetValue.md)
- [SomeIpGetValueDWord](CAPLfunctionSomeIpGetValueDWord.md)
- [SomeIpGetValueFloat](CAPLfunctionSomeIpGetValueFloat.md)
- [SomeIpGetValueInt64](CAPLfunctionSomeIpGetValueInt64.md)
- [SomeIpGetValueLong](CAPLfunctionSomeIpGetValueLong.md)
- [SomeIpGetValuePhys](CAPLfunctionSomeIpGetValuePhys.md)
- [SomeIpGetValueQWord](CAPLfunctionSomeIpGetValueQWord.md)
- [SomeIpGetValueString](CAPLfunctionSomeIpGetValueString.md)
- [SomeIpRemoveValue](CAPLfunctionSomeIpRemoveValue.md)
- [SomeIpSetRequestId](CAPLfunctionSomeIpSetRequestId.md)
- [SomeIpSetReturnCode](CAPLfunctionSomeIpSetReturnCode.md)
- [SomeIpSetValue...](CAPLfunctionSomeIpSetValue.md)
- [SomeIpSetValueDWord](CAPLfunctionSomeIpSetValueDWord.md)
- [SomeIpSetValueFloat](CAPLfunctionSomeIpSetValueFloat.md)
- [SomeIpSetValueInt64](CAPLfunctionSomeIpSetValueInt64.md)
- [SomeIpSetValueLong](CAPLfunctionSomeIpSetValueLong.md)
- [SomeIpSetValuePhys](CAPLfunctionSomeIpSetValuePhys.md)
- [SomeIpSetValueQWord](CAPLfunctionSomeIpSetValueQWord.md)
- [SomeIpSetValueString](CAPLfunctionSomeIpSetValueString.md)
- [Syntax for Database-based Access Paths](CAPLfunctionSomeIpSyntaxDatabaseAccessPath.md)
- [Syntax for Predefined Service Discovery (SD) Access Paths](CAPLfunctionSomeIpSyntaxPredefinedSDAccessPath.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)