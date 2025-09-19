[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorQueueSerialFrame.md)

# sensorQueueSerialFrame

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorQueueSerialFrame

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorQueueSerialFrame(char[] sysVarNamespace, dword data); // from 1
SensorErrorCode sensorQueueSerialFrame(char[] sysVarNamespace, dword data, dword frameSpacingNs); // from 2
```

## Description

Queues one frame for the given datum.

## Parameters

- **sysVarNamespace**: The namespace of the UART/RS485/LVDS channel the data shall be queued in.
- **data**: The datum that shall be sent.
- **frameSpacingNs**: The wait time after each sent frame in ns (default is 0). Spacing is performed with a resolution of 10µs. Intermediate values are rounded up to the next greater supported value.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Send a single frame with payload "42"
sensorQueueSerialFrame("SENSOR::UART::ExampleChannel", 42);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
