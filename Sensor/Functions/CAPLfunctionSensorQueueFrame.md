[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorQueueFrame.md)

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorQueueFrame

# sensorQueueFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorQueueFrame(char[] sysVarNamespace, byte buffer[], dword byteCount); // from 1
```

```plaintext
SensorErrorCode sensorQueueFrame(char[] sysVarNamespace, byte buffer[], dword byteCount, dword[] clockStretchNs); // from 2
```

## Description

This function is intended to be used for I2C slave simulation. It inserts the given data bytes into the response queue of the given slave.

## Parameters

- **sysVarNamespace**: The namespace of the slave the data shall be queued in.
- **buffer**: The array of bytes that shall be put into the slave’s response queue. The bytes of the array will be output in the order they are specified.
- **byteCount**: The length of the data in bytes.
- **clockStretchNs**: Array of clock stretch values in ns for each of the data bytes. The length of this array must match the length of the data byte array.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Byte array used to prepare the slave's 12 bit response
byte responseData[2] = {0x42, 0x21};

// Queue the resonse in the slave
sensorQueueFrame("SENSOR::I2C::ExampleChannel::ExampleSlave", responseData, 2);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
