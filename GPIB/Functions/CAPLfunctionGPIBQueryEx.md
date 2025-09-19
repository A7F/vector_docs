[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBQueryEx.md)

[CAPL Functions](../../CAPLfunctions.md) » [GPIB](../CAPLfunctionsGPIBOverview.md) » GPIBQueryEx

# GPIBQueryEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long GPIBQueryEx (long deviceDescriptor, char cmdStr[], long size);
```

## Description

Query to the device.

The **cmdStr** is put to a queue, and then the function returns immediately. When the **cmdStr** has been sent to the device, and a response has been received, the user-supplied function [GPIBResponse](CAPLfunctionGPIBResponse.md) is called.

## Parameters

- **deviceDescriptor**: Device ID
- **cmdStr**: Query string
- **Size**: Maximum expected size of the data to be read.

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available, or if no [GPIBResponse](CAPLfunctionGPIBResponse.md) function was supplied

## Example

Query after wave form: `GPIBQuery(myDev, "WAVF?", 1024)`

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
