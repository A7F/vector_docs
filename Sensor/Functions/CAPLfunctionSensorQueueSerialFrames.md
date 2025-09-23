[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorQueueSerialFrames.md)

**CAPL Functions** » **Sensor** » **sensorQueueSerialFrames**

# sensorQueueSerialFrames

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `SensorErrorCode sensorQueueSerialFrames(char[] sysVarNamespace, char[] data, dword dataCount); // form 1`
- `SensorErrorCode sensorQueueSerialFrames(char[] sysVarNamespace, dword[] data, dword dataCount); // form 2`
- `SensorErrorCode sensorQueueSerialFrames(char[] sysVarNamespace, dword[] data, dword dataCount, dword frameSpacingNs); // form 3`

## Description

Queues one frame for each given datum.

## Parameters

- **sysVarNamespace**: The namespace of the UART/RS485/LVDS channel the data shall be queued in.
- **data**: The array of values/characters that shall be sent (one datum per frame).
- **dataCount**: The number of data/frames to send.
- **frameSpacingNs**: The wait time after each sent frame in ns (default is 0). Spacing is performed with a resolution of 10µs. Intermediate values are rounded up to the next greater supported value.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
// Send three frames with different payloads
dword data[3] = {0x01, 0x02, 0x03};
sensorQueueSerialFrames("SENSOR::UART::ExampleChannel", data, 3);
```
