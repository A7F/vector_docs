[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionQueueWriteFrame.md)

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » QueueWriteFrame

# QueueWriteFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of I2C slaves.

## Method Syntax

```plaintext
SensorErrorCode SysVarNamespace.QueueWriteFrame(byte[] writeBuffer, dword writeByteCount); // from 1
SensorErrorCode SysVarNamespace.QueueWriteFrame(byte[] writeBuffer, dword writeByteCount, dword startDelayNs); // from 2
```

## Description

This method is intended to be used for I2C master simulation. It queues a frame to write the given bytes to the given slave.

## Parameters

- **writeBuffer**: Buffer containing the bytes to be sent to the slave.
- **writeByteCount**: Length of the write buffer in bytes.
- **startDelayNs**: Delay in ns before the frame is actually sent to the slave.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Byte array to be sent to the slave
byte sendData[2] = {0x42, 0x21};

// Queue the request to the slave
sysvar::SENSOR::I2C::ExampleChannel::ExampleSlave.QueueWriteFrame (sendData, 2);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
