# SomeIpGetProtocol

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpGetProtocol ( dword messageHandle );
```

## Description

This function returns the protocol (UDP/TCP) the SOME/IP message was transmitted with.

## Parameters

- **messageHandle**: Handle of the received SOME/IP message.

  **Note**: This function can only be called within the [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md) callback function.

## Return Values

- **Protocol**:
  - 0: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
  - 6: TCP
  - 17: UDP

## Example

```plaintext
void OnSomeIpMessage( DWORD messageHandle )
{
  DWORD protocol      = 0;
  LONG  errorCode     = 0;
  LONG  errorOccured  = 0;

  // get data from SOME/IP message
  if((protocol = SomeIpGetProtocol(messageHandle)) == 0)
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
    write("SOME/IP message with Protocol Type 0x%x (%d) received",protocol,protocol);
  } // if
}
```

[See Also](javascript:void(0);)

```markdown
