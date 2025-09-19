[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetAddressAsArray.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Address::GetAddressAsArray

# IP_Address::GetAddressAsArray

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

- `long IP_Address::GetAddressAsArray(byte ipAddr[]); // form 1`
- `long IP_Address::GetAddressAsArray(char ipAddr[]); // form 2`

## Description

Copies the current IP address to the byte array whereas the byte array's size needs to fit the current IP address value.

## Parameters

—

## Return Values

- **0**: Success
- **1**: Array size does not fit the current IP address
- **2**: Object has not been set to a valid address

## Example

```plaintext
on start
{
  IP_Address FC00::0001 addr;
  byte addrData[16];

  if(addr.SetAddressAsArray( addrData ) == 0)
  {
    // do something with addrData
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
