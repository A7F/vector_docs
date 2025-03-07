[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBChangeSecAddr.md)

**CAPL Functions** » **GPIB** » GPIBDevChangeSecAddr

# GPIBDevChangeSecAddr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long GPIBDevChangeSecAddr (long deviceDescriptor, long newAddr);
```

## Description

Changes the secondary address of a device.

## Parameters

- **deviceDescriptor**: Device ID
- **newAddr**: New secondary address

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)