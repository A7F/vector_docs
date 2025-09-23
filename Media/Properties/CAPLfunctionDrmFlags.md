# DrmFlags

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

DrmFlags

## Description

Specifies whether a video media type requires the enforcement of copy protection.

## Data Type

dword

## Remarks

The value of this property is one of the following:

- **None = 0**  
  No copy protection is required.
- **AnalogProtected = 1**  
  Analog copy protection should be applied.
- **DigitallyProtected = 2**  
  Digital copy protection should be applied.

This property provides a hint to the application. It is not used to enforce copy protection or to specify the copy protection mechanism.
