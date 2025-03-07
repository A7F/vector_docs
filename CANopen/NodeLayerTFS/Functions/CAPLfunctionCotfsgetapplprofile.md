[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCotfsgetapplprofile.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsGetApplProfile**

# coTfsGetApplProfile

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
dword coTfsGetApplProfile( void );
```

## Description

The function reads the currently set application profile.

## Parameters

—

## Return Values

Used application profile, 301 if not supported profile is used.

## Example

```plaintext
dword appProfile;
appProfile = coTfsGetApplProfile();
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)