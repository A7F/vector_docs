[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthGetReturnCode.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthGetReturnCode**

# AREthGetReturnCode

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthGetReturnCode ( dword messageHandle );
```

## Description

This function returns the Return Code from the SOME/IP message header.

## Parameters

- **messageHandle**: Handle of the SOME/IP message (e.g. see [OnAREthMessage](CAPLfunctionOnAREthMessage.md))

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

In the event of an error, the function returns the value 0. The [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```plaintext
void OnAREthMessage( dword messageHandle )
{
  dword retCode       = 0;
  LONG  errorCode     = 0;
  LONG  errorOccured  = 0;

  // get data from SOME/IP message
  if((retCode = AREthGetReturnCode(messageHandle)) == 0)
  {
    // check if last function was executed correct
    if((errorCode = AREthGetLastError()) != 0)
    {
      write("AUTOSAR Eth IL error occured: Error code: %d", errorCode);
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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
