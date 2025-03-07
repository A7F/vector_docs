[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenLssActivateBitTimingParameters.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenLssActivateBitTimingParameters

# CANopenLssActivateBitTimingParameters

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword CANopenLssActivateBitTimingParameters(dword switchDelay);
```

## Description

The LSS master activates the bit timing of a LSS slave. The bit timing can be configured using the function [CANopenLssConfigureBitTimingParameters](CAPLfunctionsCANopenLssConfigureBitTimingParameters.md).

## Parameters

- **switchDelay**: Delay in ms until the bit timing is active.

## Return Values

- **0**: Successful
- **1**: Invalid channel (not CAN or inactive)

## Example

```c
// Activate bit timing with 500ms delay
CANopenLssActivateBitTimingParameters(500);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)