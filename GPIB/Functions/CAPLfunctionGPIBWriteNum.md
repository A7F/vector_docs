[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBWriteNum.md)

**CAPL Functions** » **GPIB** » **GPIBWriteNum**

# GPIBWriteNum

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long GPIBWriteNum (long deviceDescriptor, char cmdStr[], double value);
```

## Description

Writes **cmdStr** + numeric value to the device. The function returns immediately and does not wait for the end of the command transmission.

## Parameters

- **deviceDescriptor**: Device ID
- **cmdStr**: GPIB command
- **value**: Numeric value of the parameter

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available

## Example

Setting of a voltage of 1.23 V: `GPIBWriteStr(myDev, "V", 1.23)`

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
