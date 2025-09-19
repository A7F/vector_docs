[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorQueueValues.md)

**CAPL Functions** » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorQueueValues

# sensorQueueValues

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorQueueValues (char[] sysVarName, float[] values, dword valueCount);
```

## Description

Inserts the given values into the send queue of the given sensor signal system variable.

## Parameters

- **sysVarName**: The name of the sensor signal system variable the values shall be queued in.
- **values**: Specifies the values that shall be queued.
- **valueCount**: Specifies the number of values in the given array.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
float values[10];
// Todo: fill array with signal values

sensorQueueValues("SENSOR::PSI5::ExampleChannel::ExampleSensor::ExampleTimeslot::Signals::ExampleSignal_Stim", values, 10);
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
