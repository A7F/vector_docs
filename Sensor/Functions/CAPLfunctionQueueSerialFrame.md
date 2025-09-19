[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionQueueSerialFrame.md)

# QueueSerialFrame

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » QueueSerialFrame

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of UART/RS485/LVDS channels.

## Method Syntax

- `SensorErrorCode SysVarNamespace.QueueSerialFrame(dword data); // form 1`
- `SensorErrorCode SysVarNamespace.QueueSerialFrame(dword data, dword frameSpacingNs); // form 2`

## Description

Queues one frame for the given datum.

## Parameters

- **data**: The datum that shall be sent.
- **frameSpacingNs**: The wait time after each sent frame in ns (default is 0). Spacing is performed with a resolution of 10µs. Intermediate values are rounded up to the next greater supported value.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```cpp
// Send a single frame with payload "42"
sysvar::SENSOR::UART::ExampleChannel.QueueSerialFrame(42);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
