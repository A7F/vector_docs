# SomeIpGetDestinationAddress

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword SomeIpGetDestinationAddress ( dword messageHandle ); // form 1`
- `long SomeIpGetDestinationAddress ( dword messageHandle, byte ipv6Address[] ); // form 2`

## Description

This function returns the IPv4 destination address.

## Parameters

- **messageHandle**: Handle of the received SOME/IP message.

  **Note**: This function can only be called within the [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md) callback function.

- **ipv6Address**: The parameter to which the IPv6 address will be written to.

## Return Values

- IPv4 destination address (Network Byte Order)
- In the event of an error, the function returns the value 0. The [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

  **Note**: The [IpGetAddressAsString](../../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsString.md) function can be used to convert the numerical return value to a character string in shorthand notation.

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsIPErrorCodes.md)

## Example

```c
void OnSomeIpMessage( DWORD messageHandle )
{
  DWORD dstAddress    = 0;
  LONG  errorCode     = 0;
  LONG  errorOccured  = 0;
  char  buffer[100];

  // get data from SOME/IP message
  if((dstAddress = SomeIpGetDestinationAddress(messageHandle)) == 0)
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
    IpGetAddressAsString(dstAddress, buffer, elcount(buffer));
    write("SOME/IP message received. Destination address: %s",buffer);
  } // if
}
```

[See Also](javascript:void(0);)
