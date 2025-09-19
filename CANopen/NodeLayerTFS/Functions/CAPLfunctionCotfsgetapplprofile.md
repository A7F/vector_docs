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
