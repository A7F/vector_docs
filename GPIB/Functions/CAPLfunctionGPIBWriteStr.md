[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBWriteStr.md)

**CAPL Functions** » **GPIB** » **GPIBWriteStr**

# GPIBWriteStr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long GPIBWriteStr 
(long deviceDescriptor, char cmdStr[]);
```

## Description

Writes **cmdStr** to the device. The function returns immediately and does not wait for the end of the command transmission.

## Parameters

- **deviceDescriptor**: Device ID
- **cmdStr**: GPIB command

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: on error, if no GPIB driver is available

## Example

Setting of a voltage of 1.23 V: `GPIBWriteStr(myDev, "V 1.23")`

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
