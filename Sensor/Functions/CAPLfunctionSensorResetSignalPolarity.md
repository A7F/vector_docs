[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorResetSignalPolarity.md)

## sensorResetSignalPolarity

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorResetSignalPolarity

**Valid for**: CANoe DE • CANoe4SW DE

### Note

Currently, changing the signal polarity at measurement time is only supported by SENT channels that are mapped to a VT2710 module.

### Function Syntax

```plaintext
SensorErrorCode sensorResetSignalPolarity(char[] sysVarNamespace);
```

### Description

Resets the signal polarity of a simulated sensor to the initially configured value.

### Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.

### Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

### Example

```c
enum sensorErrorCode result;

// Reset the sensor's signal polarity
result = sensorResetSignalPolarity("SENSOR::SENT::SENSORSIM::Sensor");

if (result == eSensorNoError)
{
  write("Resetting the signal polarity succeeded.");
}
else
{
  write("Resetting the signal polarity failed with code: %d", result);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)