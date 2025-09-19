[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalSetFreshness.md)

## SecurityLocalSetFreshness

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalSetFreshness

### Function Syntax

```plaintext
long SecurityLocalSetFreshness(char freshnessIdentifierString[], dword freshnessValueId, byte freshnessData[], dword freshnessDataLength, dword flags)
```

### Description

Set the freshness for the specified Id.

As freshness values differ from Security Source to Security Source, refer to the Security Source specific manual for more information about which values to specify as parameters.

### Parameters

- **char freshnessIdentifierString[]**: A string as an identifier for the freshness to set.
- **dword freshnessValueId**: A numerical Id for the freshness to set.
- **byte freshnessData[]**: The freshness to set as a byte array.
- **dword freshnessDataLength**: The length of the freshness to set in bytes.
- **dword flags**: Optional flags (depending on the Security Source).

### Return Values

- **1**: Success
- **0**: Error, no details
- **-1**: Invalid handle
- **-2**: Data incomplete
- **-3**: Signal length does not fit
- **-4**: Security source error, no details
- **-6**: Not supported
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
