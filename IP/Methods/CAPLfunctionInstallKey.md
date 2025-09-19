[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionInstallKey.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::InstallKey

# EthernetMacsecSecureEntity::InstallKey

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

```plaintext
byte EthernetMacsecSecureEntity.InstallKey(EtrhernetMacsecKeyId ki, byte [] sak, dword sakLength);
byte EthernetMacsecSecureEntity.InstallKey(EtrhernetMacsecKeyId ki, byte [] sak, dword sakLength, byte salt[], dword saltLength);
```

## Description

Installs a key under the specified key id, and with the specified key data. The key can later be referred to under its key id to create a secure association.

Note that the key id usually consists of the MKA member id and an ascending key number. If MKA is not going to be used, the key id can be initialized with any unique values.

For use with extended packet numbering (XPN), a salt value must be specified (see IEEE802.1AE for calculation of the salt value).

## Parameters

- **ki**: The key id under which the new key shall be stored.
- **sak**: The key data to be used for the SAK.
- **sakLength**: The number of bytes in the array to be used for the key. Must be either 16 or 32.
- **salt**: The optional salt value for use with XPN.
- **saltLength**: The number of bytes in the array to be used for the salt value. Must be 12.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
