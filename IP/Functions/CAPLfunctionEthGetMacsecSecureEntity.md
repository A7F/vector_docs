[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetMacsecSecureEntity.md)

## ethGetMacsecSecureEntity

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethGetMacsecSecureEntity

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

```
EthernetMacsecSecureEntity ethGetMacsecSecureEntity(ethernetPort port);
```

### Description

Returns the MACsec Secure Entity associated with the given measurement port. The measurement port must have an existing MACsec configuration to get a valid MACsec secure entity.

### Parameters

- **port**: A measurement port with an existing MACsec configuration.

### Return Values

- **EthernetMacsecSecureEntity**: The MACsec secure entity. Check with its property **isValid** if the call succeeded.

### Example

```c
EthernetMacsecSecureEntity secY1;
secY1 = ethGetMacsecSecureEntity(ethernetport::Ethernet1::Port1);
if (secY1.isValid)
{
  // use methods of EthernetMacsecSecureEntity to manipulate or query the secure entity
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
