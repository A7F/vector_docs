[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBDevOnline.md)

[CAPL Functions](../../CAPLfunctions.md) » [GPIB](../CAPLfunctionsGPIBOverview.md) » GPIBDevOnline

# GPIBDevOnline

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long GPIBDevOnline (long deviceDescriptor, long mode);
```

## Description

Activates/deactivates the device.

## Parameters

- **deviceDescriptor**: Device ID
- **mode**:
  - 1: online
  - 0: offline

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
