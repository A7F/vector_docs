[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetAddressAsArray.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Address::SetAddressAsArray

# IP_Address::SetAddressAsArray

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

- `long IP_Address::SetAddressAsArray(byte ipAddr[]);` // form 1
- `long IP_Address::SetAddressAsArray(char ipAddr[]);` // form 2

## Description

Copies the byte array to the IP address value.

## Parameters

—

## Return Values

- **0**: Success
- **1**: Array size is neither four nor sixteen

## Example

```plaintext
on start
{
  byte addrData[16] = { 0xFC, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x01 };
  IP_Address addr;

  if(addr.SetAddressAsArray( addrData ) == 0)
  {
    // do something with addrData
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
