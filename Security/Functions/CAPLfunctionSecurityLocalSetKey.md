[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalSetKey.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalSetKey

# SecurityLocalSetKey

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalSetKey(char keyIdentifierString[], dword keyIdentifierValue, byte newKey[], dword keyLength, dword flags)
```

## Description

Changes a key at the node.

As keys and the key handling differs from Security Source to Security Source you have to refer to the Security Source specific manual to get more information about which values you have to specify as parameters.

## Parameters

- **char keyIdentifierString[]**: A string as an identifier for the key to set.
- **dword keyIdentifierValue**: A numerical Id for the key to set.
- **byte newKey[]**: The key to set as a byte array.
- **dword keyLength**: The length of the new key in bytes.
- **dword flags**: Optional flags (depending on the Security Source).

## Return Values

A Value of 1 means that the action was successful. A value less than or equal to 0 means error.

- **1**: Success.
- **0**: Error, no details.
- **-1**: Invalid handle.
- **-2**: Data incomplete.
- **-3**: Signal length does not fit.
- **-4**: Security source error, no details.
- **-6**: Not supported.
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
