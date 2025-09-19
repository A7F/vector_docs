# coTfsGetVersion

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword coTfsGetVersion( void );
```

## Description

This function returns the internal version number of this CANopen Test Feature Set node layer.

## Parameters

—

## Return Values

Version number

## Example

```c
dword majorVersion;
dword minorVersion;

minorVersion = coTfsGetVersion();
majorVersion = (minorVersion >> 8) & 0xFF;
minorVersion = minorVersion & 0xFF;

write("coTfs node layer version = %d.%d", majorVersion, minorVersion);
```
