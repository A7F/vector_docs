[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenLssConfigureBitTimingParameters.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenLssConfigureBitTimingParameters

# CANopenLssConfigureBitTimingParameters

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword CANopenLssConfigureBitTimingParameters (byte tableSelector, byte tableIndex);
```

## Description

The LSS master configures the bit timing of a LSS slave.

## Parameters

- **tableSelector**: 
  - **0**: bit timing table according to CiA 301
  - **0x80..0xFE**: manufacturer-specific bit timing table

- **tableIndex**: Index of the bit timing table to be used.

## Return Values

- **0**: Successful
- **1**: Invalid channel (not CAN or inactive)

## Example

```c
// Set bit timing to 125kBit/s
CANopenLssConfigureBitTimingParameters(0, 4);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)