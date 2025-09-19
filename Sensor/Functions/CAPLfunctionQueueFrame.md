[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionQueueFrame.md)

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » QueueFrame

# QueueFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of I2C slaves.

## Method Syntax

- `SensorErrorCode SysVarNamespace.QueueFrame(byte buffer[], dword byteCount); // form 1`
- `SensorErrorCode SysVarNamespace.QueueFrame(byte buffer[], dword byteCount, dword[] clockStretchNs); // from 2`

## Description

This method is intended to be used for I2C slave simulation. It inserts the given data bytes into the response queue of the given slave.

## Parameters

- **buffer**: The array of bytes that shall be put into the slave’s response queue. The bytes of the array will be output in the order they are specified.
- **byteCount**: The length of the data in bytes.
- **clockStretchNs**: Array of clock stretch values in ns for each of the data bytes. The length of this array must match the length of the data byte array. The maximum allowed value for each array element is 16376000, which corresponds to 16.376ms.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
// Byte array used to prepare the slave's 2 byte response
byte responseData[2] = {0x42, 0x21};

// Queue the response in the slave
sysvar::SENSOR::I2C::ExampleChannel::ExampleSlave.QueueFrame (responseData, 2);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
