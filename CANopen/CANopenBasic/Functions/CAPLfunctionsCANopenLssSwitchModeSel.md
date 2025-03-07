[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenLssSwitchModeSel.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenLssSwitchModeSel

# CANopenLssSwitchModeSel

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword CANopenLssSwitchModeSel (dword vendorId, dword productCode, dword revisionNo, dword serialNo);
```

## Description

Sets LSS slaves to the configuration mode or leave the mode.

## Parameters

- **vendorId**: Vendor Id of the device.
- **productCode**: Product code of the device.
- **revisionNo**: Revision number of the device.
- **serialNo**: Serial number of the device.

## Return Values

- **0**: Successful
- **1**: Invalid channel (not CAN or inactive)

## Example

```c
// Switch a device with vendor-ID 5, product code 0, revision number 1 and serial number 123 to configuration mode
CANopenLssSwitchModeSel(5, 0, 1, 123);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)