[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthGetProtocolVersion.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthGetProtocolVersion**

# AREthGetProtocolVersion

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AREthGetProtocolVersion ( dword messageHandle );
```

## Description

This function returns the Protocol Version from the SOME/IP message header.

## Parameters

- **messageHandle**: Handle of the SOME/IP message (e.g. see [OnAREthMessage](CAPLfunctionOnAREthMessage.md))

## Return Values

- **Protocol version**: In the event of an error, the function returns the value 0. The [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```c
void OnAREthMessage( dword messageHandle )
{
  dword protVers     = 0;
  LONG  errorCode    = 0;
  LONG  errorOccured = 0;

  // get data from SOME/IP message
  if((protVers = AREthGetProtocolVersion(messageHandle)) == 0)
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
    write("SOME/IP message with Protocol Version 0x%02x (%d) received",protVers,protVers);
  } // if
}
```

[See Also](javascript:void(0);)
