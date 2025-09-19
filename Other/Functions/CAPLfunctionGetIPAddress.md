[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetIPAddress.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » GetIPAddress

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
