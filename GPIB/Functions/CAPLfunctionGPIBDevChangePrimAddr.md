[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBDevChangePrimAddr.md)

**CAPL Functions** » [GPIB](../CAPLfunctionsGPIBOverview.md) » GPIBDevChangePrimAddr

# GPIBDevChangePrimAddr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long GPIBDevChangePrimAddr (long deviceDescriptor, long newAddr);
```

## Description

Changes the primary address of a device.

## Parameters

- **deviceDescriptor**: Device ID
- **newAddr**: New primary address

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)