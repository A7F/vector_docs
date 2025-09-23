# QueueReadFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of I2C slaves.

## Method Syntax

```plaintext
SensorErrorCode SysVarNamespace.QueueReadFrame(dword readByteCount); // from 1
SensorErrorCode SysVarNamespace.QueueReadFrame(dword readByteCount, dword startDelayNs); // form 2
```

## Description

This method is intended to be used for I2C master simulation. It queues a frame to read the given number of bytes from the given slave.

## Parameters

- **readByteCount**: The number of bytes to read from the slave.
- **startDelayNs**: Delay in ns before the frame is actually sent to the slave.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Queue a request to read 4 bytes from the slave
sysvar::SENSOR::I2C::ExampleChannel::ExampleSlave.QueueReadFrame (4);
```
