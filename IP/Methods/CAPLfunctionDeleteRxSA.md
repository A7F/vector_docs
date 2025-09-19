[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionDeleteRxSA.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::DeleteRxSA

# EthernetMacsecSecureEntity::DeleteRxSA

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.DeleteRxSA(EthernetMacsecSCI sci, byte AN);`

## Description

Deletes a secure association for receiving.

## Parameters

- **sci**: The secure channel id of the secure channel of this SA to be deleted.
- **AN**: The secure association number of the SA to be deleted.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

The call will fail if:

- The secure channel referred to by the sci does not exist.
- The AN is not in range 0..3.
- The SA referred to by the association number does not exist.

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
