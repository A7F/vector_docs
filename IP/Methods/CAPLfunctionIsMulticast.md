[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionIsMulticast.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **IP_Address::IsMulticast**

# IP_Address::IsMulticast

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Method Syntax

long [IP_Address](../Objects/CAPLfunctionIPAdredress.md)::IsMulticast();

## Description

Checks if the current address is a multicast address.

## Parameters

—

## Return Values

Returns 1 if the object’s address value is a multicast address.

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
