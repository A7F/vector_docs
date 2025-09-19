[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetSourceAddress.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpGetSourceAddress**

# SomeIpGetSourceAddress

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpGetSourceAddress ( dword messageHandle ); // form 1
long SomeIpGetSourceAddress ( dword messageHandle, byte ipv6Address[] ); // form 2
```

## Description

This function returns the IPv4 sender address.

## Parameters

- **messageHandle**: Handle of the SOME/IP message.

  **Note**: This function can only be called within the [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md) callback function.

- **ipv6Address**: The parameter to which the IPv6 address will be written to.

## Return Values

- IPv4 sender address (Network Byte Order) as numeric value.
- In the event of an error, the function returns the value 0. The [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

  **Note**: The [IpGetAddressAsString](../../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsString.md) function can be used to convert the numerical return value to a character string in shorthand notation.

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsIPErrorCodes.md)

## Example

```plaintext
void OnSomeIpMessage( DWORD messageHandle )
{
  DWORD srcAddress    = 0;
  LONG  errorCode     = 0;
  LONG  errorOccured  = 0;
  char  buffer[100];

  // get data from SOME/IP message
  if((srcAddress = SomeIpGetSourceAddress(messageHandle)) == 0)
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
    IpGetAddressAsString(srcAddress, buffer, elcount(buffer));
    write("SOME/IP message from source address %s received",buffer);
  } // if
}
```

[See Also](javascript:void(0);)
