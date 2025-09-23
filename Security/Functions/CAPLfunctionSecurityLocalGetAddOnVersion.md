[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalGetAddOnVersion.md)

## CAPL Functions » Security » SecurityLocalGetAddOnVersion

### Function Syntax

`SecurityLocalGetAddOnVersion(dword* major, dword* minor, dword* patch, dword* developmentNumber)`

### Description

Get version of the loaded add-on.

### Parameters

- **dword major [OUT]**: Major version
- **dword minor [OUT]**: Minor version
- **dword patch [OUT]**: Patch version
- **dword developmentNumber [OUT]**: Development number

### Return Values

- **1**: Success
- **0**: Failed

### Example

```c
dword result;
dword major;
dword minor;
dword patch;
dword developmentNumber;
result = SecurityLocalGetAddOnVersion(major, minor, patch, developmentNumber);
```
