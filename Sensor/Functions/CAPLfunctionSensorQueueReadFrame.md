# sensorQueueReadFrame

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorQueueReadFrame.md)

**CAPL Functions** » **Sensor** » **sensorQueueReadFrame**

## Function Syntax

```plaintext
SensorErrorCode sensorQueueReadFrame(char[] sysVarNamespace, dword readByteCount); // from 1
SensorErrorCode sensorQueueReadFrame(char[] sysVarNamespace, dword readByteCount, dword startDelayNs); // from 2
```

## Description

This function is intended to be used for I2C master simulation. It queues a frame to read the given number of bytes from the given slave.

## Parameters

- **sysVarNamespace**: The namespace of the slave the data shall be queued in.
- **readByteCount**: The number of bytes to read from the slave.
- **startDelayNs**: Delay in ns before the frame is actually sent to the slave.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Queue a request to read 4 bytes from the slave
sensorQueueFrame("SENSOR::I2C::ExampleChannel::ExampleSlave", 4);
```
