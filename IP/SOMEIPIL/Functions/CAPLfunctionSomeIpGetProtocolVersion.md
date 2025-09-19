[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetProtocolVersion.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpGetProtocolVersion**

# SomeIpGetProtocolVersion

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword SomeIpGetProtocolVersion ( dword messageHandle );
```

## Description

This function returns the Protocol Version from the SOME/IP message header.

## Parameters

- **messageHandle**: Handle of the SOME/IP message (e.g. see [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md))

## Return Values

- **Protocol version**: In the event of an error, the function returns the value 0. The [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```c
void OnSomeIpMessage( DWORD messageHandle )
{
  DWORD protVers     = 0;
  LONG  errorCode    = 0;
  LONG  errorOccured = 0;

  // get data from SOME/IP message
  if((protVers = SomeIpGetProtocolVersion(messageHandle)) == 0)
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
    write("SOME/IP message with Protocol Version 0x%02x (%d) received",protVers,protVers);
  } // if
}
```

[See Also](javascript:void(0);)
