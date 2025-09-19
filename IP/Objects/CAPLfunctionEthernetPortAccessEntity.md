[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Objects/CAPLfunctionEthernetPortAccessEntity.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetPortAccessEntity

# EthernetPortAccessEntity

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
EthernetPortAccessEntity <variable name>;
```

## Description

Defines a variable of type **EthernetPortAccessEntity**. An EthernetPortAccessEntity can be used to access the configuration and activation state of the MACsec key agreement (MKA) and the Extensible Authentication Protocol (EAP) configured on a measurement port.

To be used, a variable of this type must be initialized using the function [ethGetPortAccessEntity](../Functions/CAPLfunctionethGetPortAccessEntity.md). Successful initialization can be verified using the isValid property.

The MKA protocol can be activated or deactivated using the selector **active**. When activated, the MKA (or EAP) protocol starts when the Ethernet Link is up. When the Ethernet Link is down while the PAE is activated, the MKA instance will start operating only after the Ethernet link goes up. Vice versa, if the Ethernet goes up while the PAE is deactivated, the MKA instance will stay silent.

## Parameters

- **name**: Variable name

## Selectors

- **isValid**: 1 if the secure entity has been correctly initialized, 0 otherwise
  - Type: byte
  - Access Limitation: Read only

- **hwPort**: The measurement port this secure entity is associated with
  - Type: ethernetPort
  - Access Limitation: Read only

- **active**: Determines whether the PAE is active
  - Type: int
  - Access Limitation: Read-write

- **macsecConfig**: The MACsec/MKA configuration of this PAE
  - Type: EthernetMacsecConfiguration
  - Access Limitation: Read only

## Example

—

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
