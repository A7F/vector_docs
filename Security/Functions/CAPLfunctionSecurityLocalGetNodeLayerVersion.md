[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalGetNodeLayerVersion.md)

# SecurityLocalGetNodeLayerVersion

[CAPL Functions](../../CAPLfunctions.md) » Security » SecurityLocalGetNodeLayerVersion

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalGetNodeLayerVersion(long versionMajor, long versionMinor, long versionPatch)
```

## Description

Get NodeLayer version.

## Parameters

- **long versionMajor [Out]**: Major version number.
- **long versionMinor [Out]**: Minor version number.
- **long versionPatch [Out]**: Number of the patch.

## Return Values

- **1**: Success  
  A Value of 1 means that the action was successful.

A value less than or equal to 0 means error.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
