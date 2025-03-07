[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionResetClockTickLength.md)

**CAPL Functions** » [Sensor](../CAPLfunctionsSensorOverview.md) » ResetClockTickLength

# ResetClockTickLength

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variables belonging to the SENSOR::SENT namespace.

## Method Syntax

SensorErrorCode sysvarSensorNamespace.ResetClockTickLength();

## Description

Resets the clock tick length of a simulated sensor to the initially configured value.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Reset the sensor's tick length to the configured value.
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.ResetClockTickLength();

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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)