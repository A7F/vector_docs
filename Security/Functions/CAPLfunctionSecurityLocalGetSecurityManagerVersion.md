[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalGetSecurityManagerVersion.md)

## CAPL Functions » Security » SecurityLocalGetSecurityManagerVersion

### SecurityLocalGetSecurityManagerVersion

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

`SecurityLocalGetSecurityManagerVersion(dword* major, dword* minor, dword* patch, dword* developmentNumber)`

### Description

Get version of the loaded Security Manager.

### Parameters

- **dword major [OUT]**: Major version
- **dword minor [OUT]**: Minor version
- **dword patch [OUT]**: Patch version
- **dword developmentNumber [OUT]**: Development number

### Return Values

- **1**: Success
- **0**: Failed

### Example

```plaintext
dword result;
dword major;
dword minor;
dword patch;
dword developmentNumber;
result = SecurityLocalGetSecurityManagerVersion(major, minor, patch, developmentNumber);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
