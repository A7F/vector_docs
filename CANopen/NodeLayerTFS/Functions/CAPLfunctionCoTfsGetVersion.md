[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsGetVersion.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsGetVersion**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)