[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetValidateFrames.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetValidateFrames

# EthernetMacsecSecureEntity::GetValidateFrames

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.GetValidateFrames(EthernetMacsecValidateFrames& validateFrames);`

## Description

Returns the ValidateFrames setting. The value will be one of:

- **Disabled** – Unencrypted frames will not be validated. Instead, the SecTAG and ICV will just be stripped if present. Invalid encrypted frames will never be forwarded.
- **Checked** – MACsec frame Validation takes place, but invalid, unencrypted frames will still be forwarded. Invalid encrypted frames will never be forwarded.
- **Strict** – Invalid frames will always be dropped.

## Parameters

- **validateFrames**: The reference parameter where the queried value will be returned.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)