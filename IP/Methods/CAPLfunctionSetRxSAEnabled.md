[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetRxSAEnabled.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **EthernetMacsecSecureEntity::SetRxSAEnabled**

# EthernetMacsecSecureEntity::SetRxSAEnabled

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.SetRxSAEnabled(EthernetMacsecSCI sci, byte AN, uint8_t enabled);`

## Description

Enables or disables use of an existing secure association for receiving.

Note that up to four SAs may be enabled at the same time. A MKA key Server will usually cycle through association numbers 0 to 3 while rekeying takes place, creating, enabling, disabling and deleting the secure associations signalled by the counterpart transmitting participant.

## Parameters

- **sci**: The secure channel id of the secure channel where this SA is part of.
- **AN**: The secure association number for the SA to be enabled or disabled.
- **enabled**: Specifies whether to enable or disable transmission for this SA.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

The call will fail if:

- The secure channel referred to by the sci does not exist.
- The AN is not in range 0..3.

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
