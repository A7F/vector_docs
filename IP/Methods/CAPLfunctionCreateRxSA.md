[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionCreateRxSA.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **EthernetMacsecSecureEntity::CreateRxSA**

# EthernetMacsecSecureEntity::CreateRxSA

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
byte EthernetMacsecSecureEntity.CreateRxSA(EthernetMacsecSCI sci, byte AN, EthernetMacsecKeyId ki);
```

## Description

Creates a secure association for receiving.

## Parameters

- **sci**: The secure channel id of the secure channel where this SA shall be created.
- **AN**: The secure association number for the SA to be created.
- **ki**: The id of a key previously installed using [InstallKey](CAPLfunctionInstallKey.md).

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

The call will fail if:

- The secure channel referred to by the sci does not exist.
- The AN is not in range 0..3.
- The key referred to by the specified key id has not been installed.
- The SA already exists.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)