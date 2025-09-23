# GetIPAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long GetIPAddress(char buffer[], dword bufferSize);
```

## Description

Retrieves the default (first) IP address of the computer as a string.

## Parameters

- **buffer**: Space for the returned address.
- **bufferSize**: Length of the buffer.

## Return Values

0 if the function completed successfully, else unequal 0.

## Example

```plaintext
char buffer[50];
GetIPAddress(buffer, elcount(buffer));
write("IP Address: %s", buffer);
```

[IpGetAdapterAddress](../../TCPIPAPI/Functions/CAPLfunctionIPGetAdapterAddress.md) • [IpGetAdapterAddressAsString](../../TCPIPAPI/Functions/CAPLfunctionIPGetAdapterAddressAsString.md) • [IpGetAddressAsNumber](../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsNumber.md) • [IpGetAddressAsArray](../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsArray.md) • [IpGetAddressAsString](../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsString.md)
