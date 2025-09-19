[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetToUDP.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **IP_Endpoint::SetToUDP**

# IP_Endpoint::SetToUDP

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

long [IP_Endpoint](../Objects/CAPLfunctionIPEndpoint.md)::SetToUDP();

## Description

Sets the transport protocol to UDP.

## Parameters

—

## Return Values

- **0**: Success

## Example

```plaintext
on start
{
  IP_Endpoint 192.168.1.1:4000 addr;
  addr.SetToUDP();
  if (addr.IsUDP())
  {
    write("Is UDP endpoint");
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
