[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenLssSwitchModeGlob.md)

## CANopenLssSwitchModeGlob

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenLssSwitchModeGlob

### Function Syntax

```
dword CANopenLssSwitchModeGlob (byte mode);
```

### Description

Sets LSS slaves to the configuration mode or leave the mode.

### Parameters

- **mode**  
  - **0**: Switch to global configuration mode waiting, i.e. leaves the configuration mode.
  - **1**: Switch the LSS slaves to configuration mode.

### Return Values

- **0**: Successful
- **1**: Invalid channel (not CAN or inactive)

### Example

—

[Feature availability for your product](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
