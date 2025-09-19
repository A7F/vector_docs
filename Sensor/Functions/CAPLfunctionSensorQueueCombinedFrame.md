[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorQueueCombinedFrame.md)

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorQueueCombinedFrame

# sensorQueueCombinedFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorQueueCombinedFrame(char[] sysVarNamespace, byte[] writeBuffer, dword writeBufferCount, dword readByteCount); // from 1
```

```plaintext
SensorErrorCode sensorQueueCombinedFrame(char[] sysVarNamespace, byte[] writeBuffer, dword writeBufferCount, dword readByteCount, dword startDelayNs); // from 2
```

## Description

This function is intended to be used for I2C master simulation. It queues a frame to write and then read the given number of bytes from the given slave.

## Parameters

- **writeBuffer**: Buffer containing the bytes to be sent to the slave.
- **writeByteCount**: Length of the write buffer in bytes.
- **readByteCount**: The number of bytes to read from the slave.
- **startDelayNs**: Delay in ns before the frame is actually sent to the slave.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Byte array to be sent to the slave
byte sendData[2] = {0x42, 0x21};

// Send the prepared byte array to the slave, then read 4 bytes from the slave
sensorQueueCombinedFrame ("SENSOR::I2C::ExampleChannel::ExampleSlave", sendData, 2, 4);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
