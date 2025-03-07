[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthGetRequestId.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthGetRequestId**

# AREthGetRequestId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthGetRequestId ( dword messageHandle );
```

## Description

This function returns the Request ID from the SOME/IP message header.

## Parameters

- **messageHandle**: Handle of the SOME/IP message (e.g. see [OnAREthMessage](CAPLfunctionOnAREthMessage.md))

## Return Values

- **Request ID**: In the event of an error, the function returns the value 0. The [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```plaintext
void OnAREthMessage( dword messageHandle )
{
  dword requestId    = 0;
  LONG  errorCode    = 0;
  LONG  errorOccured = 0;

  // get data from SOME/IP message
  if((requestId = AREthGetRequestId(messageHandle)) == 0)
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
    write("SOME/IP message with Request ID 0x%08x received",requestId);
  } // if
}
```

[See Also](javascript:void(0);)
```markdown
AREthFillValues
AREthGetDestinationAddress
AREthGetDestinationPort
AREthGetInterfaceVersion
AREthGetLength
AREthGetMessageId
AREthGetMessageType
AREthGetProtocol
AREthGetProtocolVersion
AREthGetRequestId
AREthGetReturnCode
AREthGetSourceAddress
AREthGetSourcePort
AREthGetValue...
AREthGetValueDWord
AREthGetValueFloat
AREthGetValueInt64
AREthGetValueLong
AREthGetValuePhys
AREthGetValueQWord
AREthGetValueString
AREthSetRequestId
AREthSetReturnCode
AREthSetValue...
AREthSetValueDWord
AREthSetValueFloat
AREthSetValueInt64
AREthSetValueLong
AREthSetValuePhys
AREthSetValueQWord
AREthSetValueString
Syntax for Database-based Access Paths
Syntax for Predefined Service Discovery (SD) Access Paths
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)