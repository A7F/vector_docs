# SomeIpGetDestinationPort

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpGetDestinationPort ( dword messageHandle );
```

## Description

This function returns the destination port (UDP/TCP).

## Parameters

- **messageHandle**: Handle of the received SOME/IP message

  **Note**: This function can only be called within the [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md) callback function.

## Return Values

- **Destination port**: In the event of an error, the function returns the value 0. The [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```plaintext
void OnSomeIpMessage( DWORD messageHandle )
{
  DWORD dstPort       = 0;
  LONG  errorCode     = 0;
  LONG  errorOccured  = 0;

  // get data from SOME/IP message
  if((dstPort = SomeIpGetDestinationPort(messageHandle)) == 0)
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
    write("SOME/IP message received. Destination Port: %d",dstPort);
  } // if
}
```

[See Also](javascript:void(0);)

```markdown
- [SomeIpFillValues](CAPLfunctionSomeIpFillValues.md)
- [SomeIpGetDestinationAddress](CAPLfunctionSomeIpGetDestinationAddress.md)
- [SomeIpGetInterfaceVersion](CAPLfunctionSomeIpGetInterfaceVersion.md)
- [SomeIpGetLength](CAPLfunctionSomeIpGetLength.md)
- [SomeIpGetMessageId](CAPLfunctionSomeIpGetMessageId.md)
- [SomeIpGetMessageType](CAPLfunctionSomeIpGetMessageType.md)
- [SomeIpGetProtocol](CAPLfunctionSomeIpGetProtocol.md)
- [SomeIpGetProtocolVersion](CAPLfunctionSomeIpGetProtocolVersion.md)
- [SomeIpGetRequestId](CAPLfunctionSomeIpGetRequestId.md)
- [SomeIpGetReturnCode](CAPLfunctionSomeIpGetReturnCode.md)
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
```
