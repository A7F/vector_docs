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
