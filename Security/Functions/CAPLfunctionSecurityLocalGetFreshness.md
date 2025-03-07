[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalGetFreshness.md)

# SecurityLocalGetFreshness

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalGetFreshness

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalGetFreshness(char freshnessIdentifierString[], dword freshnessValueId, byte freshnessData[], dword freshnessDataLength)
```

## Description

Gets the freshness value for the specified Id.

As freshness values differ from Security Source to Security Source, refer to the Security Source specific manual for more information about which values you need to specify as parameters.

## Parameters

- **char freshnessIdentifierString[]**: A string as an identifier for the freshness to get.
- **dword freshnessValueId**: A numerical Id for the freshness to get.
- **byte freshnessData[] [In/Out]**: The buffer for the freshness to get.
- **dword freshnessDataLength [In/Out]**: The length of the buffer for the freshness to get in bytes.

## Return Values

A Value of 1 means that the action was successful. A value less than or equal to 0 means error.

- **1**: Success
- **0**: Error, no details
- **-1**: Invalid handle
- **-2**: Data incomplete
- **-3**: Signal length does not fit
- **-4**: Security source error, no details
- **-6**: Not supported
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)