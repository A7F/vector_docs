[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorResetClockTickLength.md)

## sensorResetClockTickLength

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorResetClockTickLength

### Function Syntax

```plaintext
SensorErrorCode sensorResetClockTickLength(char[] sysVarNamespace);
```

### Description

Resets the clock tick length of a simulated sensor to the initially configured value.

### Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.

### Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

### Example

```plaintext
enum sensorErrorCode result;

// Reset the sensor's tick length to the configured value.
result = sensorResetClockTickLength("SENSOR::SENT::SENSORSIM::Sensor");

if (result == eSensorNoError)
{
  write("Sensor clock tick length reset successfully.");
}
else
{
  write("Resetting sensor clock tick length failed with code: %d", result);
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
