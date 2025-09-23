# GPIBQuery

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
Data up to the size of 1000 bytes are read with this function. To read more data bytes please use function [GPIBQueryEx](CAPLfunctionGPIBQueryEx.md).

## Function Syntax

`long GPIBQuery (long deviceDescriptor, char cmdStr[]);`

## Description

Query to the device.

The **cmdStr** is put to a queue, and then the function returns immediately. When the **cmdStr** has been sent to the device, and a response has been received, the user-supplied function [GPIBResponse](CAPLfunctionGPIBResponse.md) is called.

## Parameters

- **deviceDescriptor**: Device ID
- **cmdStr**: Query string

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available, or if no [GPIBResponse](CAPLfunctionGPIBResponse.md) function was supplied

## Example

**Query of the voltage:** `GPIBQuery(myDev, "V?")`
