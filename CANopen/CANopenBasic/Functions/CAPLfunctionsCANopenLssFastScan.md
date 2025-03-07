[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenLssFastScan.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenLssFastScan

# CANopenLssFastScan

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword CANopenLssFastScan (dword vendorID, dword productCode, dword revisionNumber, dword timeout);
```

## Description

The LSS master starts a LSS fast scan to identify and unconfigured LSS slave.

## Parameters

- **vendorID**: Vendor-ID of the device.
- **productCode**: Product code of the device.
- **revisionNumber**: Revision number of the device.
- **timeout**: Distance between each LSS message of the fast scan in ms.

## Return Values

- **0**: Successful
- **1**: Invalid channel (not CAN or inactive)

## Example

```c
// Start a LSS fast scan from vendor-ID 5, product code 0 and revision number 1
CANopenLssFastScan(5, 0, 1, 10);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)