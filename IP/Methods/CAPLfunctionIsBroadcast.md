[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionIsBroadcast.md)

# IP_Address::IsBroadcast

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Address::IsBroadcast

**Valid for:** CANoe DE • CANoe4SW DE

## Method Syntax

`long [IP_Address](../Objects/CAPLfunctionIPAdredress.md)::IsBroadcast();`

## Description

Checks if the current address is a broadcast address.

## Parameters

—

## Return Values

Returns 1 if the object’s address value is a broadcast address.

## Example

```plaintext
on start
{
  DoSomething( IP_Address(239.0.0.1) );
}

void DoSomething( IP_Address addr )
{
  if (addr.IsMulticast())
  {
    // ...
  }
  else if (addr.IsBroadcast())
  {
    // ...
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
