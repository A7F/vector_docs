[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetTxSAEnabled.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetTxSAEnabled

# EthernetMacsecSecureEntity::GetTxSAEnabled

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

```plaintext
byte EthernetMacsecSecureEntity.GetTxSAEnabled(EthernetMacsecSCI sci, byte AN, uint8_t& enabled);
```

## Description

Gets the enable state of the specified transmit secure association.

## Parameters

- **sci**: The secure channel id of the secure channel where this SA is part of.
- **AN**: The secure association number for the SA to be queried.
- **enabled**: Returns the enable state of this SA.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise. The call will fail if:
  - The secure channel referred to by the sci does not exist.
  - The AN is not in range 0..3.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
