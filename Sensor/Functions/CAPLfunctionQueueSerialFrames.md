[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionQueueSerialFrames.md)

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » QueueSerialFrames

# QueueSerialFrames

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of UART/RS485/LVDS channels.

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- `SensorErrorCode SysVarNamespace.QueueSerialFrames(char[] data, dword dataCount); // from 1`
- `SensorErrorCode SysVarNamespace.QueueSerialFrames(dword[] data, dword dataCount); // from 2`
- `SensorErrorCode SysVarNamespace.QueueSerialFrames(dword[] data, dword dataCount, dword frameSpacingNs); // from 3`

## Description

Queues one frame for each given datum.

## Parameters

- **data**: The array of values or characters that shall be sent (one datum per frame).
- **dataCount**: The number of data/frames to send.
- **frameSpacingNs**: The wait time after each sent frame in ns (default is 0). Spacing is performed with a resolution of 10µs. Intermediate values are rounded up to the next greater supported value.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Send three frames with different payloads
dword data[3] = {0x01, 0x02, 0x03};
sysvar::SENSOR::UART::ExampleChannel.QueueSerialFrames(data, 3);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)