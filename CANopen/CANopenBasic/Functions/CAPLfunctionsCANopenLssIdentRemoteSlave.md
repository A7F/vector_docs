[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenLssIdentRemoteSlave.md)

**Structure Path:** [CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenLssIdentRemoteSlave

# CANopenLssIdentRemoteSlave

**Valid for:** [CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword CANopenLssIdentRemoteSlave (dword vendorId, dword productCode, dword revisionNoLow, dword revisionNoHigh, dword serialNoLow, dword serialNoHigh);
```

## Description

The LSS master commands all LSS slaves whose LSS address matches the transmitted LSS address parameters to identify themselves.

## Parameters

- **vendorID**: Vendor-ID of the device.
- **productCode**: Product code of the device.
- **revisionNoLow**: Lower limit of the revision number.
- **revisionNoHigh**: Upper limit of the revision number.
- **serialNoLow**: Lower limit of the serial number.
- **serialNoHigh**: Upper limit of the serial number.

## Return Values

- **0**: Successful
- **1**: Invalid channel (not CAN or inactive)
- **4**: Invalid high limit of the serial number
- **5**: Invalid high limit of the revision number

## Example

```c
// Identify all LSS slaves of vendor ID 5 and product code 100 with a certain range of revision [0..3] and serial number [10...20]
CANopenLssIdentRemoteSlave(5, 100, 0, 3, 10, 20)
```

© Vector Informatik GmbH

**Version:** CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)