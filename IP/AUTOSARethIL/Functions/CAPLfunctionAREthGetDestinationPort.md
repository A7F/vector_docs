# AREthGetDestinationPort

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AREthGetDestinationPort ( dword messageHandle );
```

## Description

This function returns the destination port (UDP/TCP).

## Parameters

- **messageHandle**: Handle of the received SOME/IP message

  **Note**: This function can only be called within the [OnAREthMessage](CAPLfunctionOnAREthMessage.md) callback function.

## Return Values

- **Destination port**: In the event of an error, the function returns the value 0. The [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

```c
void OnAREthMessage( dword messageHandle )
{
  dword dstPort       = 0;
  LONG  errorCode     = 0;
  LONG  errorOccured  = 0;

  // get data from SOME/IP message
  if((dstPort = AREthGetDestinationPort(messageHandle)) == 0)
  {
    // check if last function was executed correct
    if((errorCode = AREthGetLastError()) != 0)
    {
      write("AUTOSAR Eth IL error occured: Error code: %d", errorCode);
      errorOccured = 1;
    }
  }

  if(errorOccured == 0)
  {
    write("SOME/IP message received. Destination Port: %d",dstPort);
  }
}
```

[See Also](javascript:void(0);)
