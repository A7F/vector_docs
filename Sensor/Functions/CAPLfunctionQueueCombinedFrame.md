# QueueCombinedFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of I2C slaves.

## Method Syntax

```plaintext
SensorErrorCode SysVarNamespace.QueueCombinedFrame(byte[] writeBuffer, dword writeBufferCount, dword readByteCount); // from 1
SensorErrorCode SysVarNamespace.QueueCombinedFrame(byte[] writeBuffer, dword writeBufferCount, dword readByteCount, dword startDelayNs); // from 2
```

## Description

This method is intended to be used for I2C master simulation. It queues a frame to write and then read the given number of bytes from the given slave.

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
sysvar::SENSOR::I2C::ExampleChannel::ExampleSlave.QueueCombinedFrame (sendData, 2, 4);
```
