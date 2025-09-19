[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorQueueWriteFrame.md)

### CAPL Functions » Sensor » sensorQueueWriteFrame

## sensorQueueWriteFrame

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorQueueWriteFrame

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
SensorErrorCode sensorQueueWriteFrame(char[] sysVarNamespace, byte[] writeBuffer, dword writeByteCount); // from 1
SensorErrorCode sensorQueueWriteFrame(char[] sysVarNamespace, byte[] writeBuffer, dword writeByteCount, dword startDelayNs); // from 2
```

### Description

This function is intended to be used for I2C master simulation. It queues a frame to write the given bytes to the given slave.

### Parameters

- **sysVarNamespace**: The namespace of the slave the data shall be queued in.
- **writeBuffer**: Buffer containing the bytes to be sent to the slave.
- **writeByteCount**: Length of the write buffer in bytes.
- **startDelayNs**: Delay in ns before the frame is actually sent to the slave.

### Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

### Example

```plaintext
// Byte array to be sent to the slave
byte sendData[2] = {0x42, 0x21};

// Queue the request to the slave
sensorQueueWriteFrame ("SENSOR::I2C::ExampleChannel::ExampleSlave", sendData, 2);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
