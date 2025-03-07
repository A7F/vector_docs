[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetTransportProtocolToUnknown.md)

## IP_Endpoint::SetTransportProtocolToUnknown

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Endpoint::SetTransportProtocolToUnknown

**Valid for:** CANoe DE • CANoe4SW DE

### Method Syntax

```plaintext
long IP_Endpoint::SetTransportProtocolToUnknown();
```

### Description

Invalidates the transport protocol.

### Parameters

—

### Return Values

- **0**: Success

### Example

```plaintext
on start
{
  IP_Endpoint UDP:192.168.1.1:4000 addr;
  addr.SetTransportProtocolToUnknown();
  if (addr.IsTCP())
  {
    write( "Is TCP endpoint" );
  }
  else if (addr.IsUDP())
  {
    write( "Is UDP endpoint" );
  }
  else
  {
    write( "No transport protocol specified for endpoint" );
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)