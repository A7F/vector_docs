# sensorSetClockTickLength

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorSetClockTickLength.md)

**CAPL Functions** » **Sensor** » **sensorSetClockTickLength**

## Valid for: CANoe DE • CANoe4SW DE

### Note
Currently, changing the tick rate at measurement time is only supported by SENT channels that are mapped to a VT2710 module. The tick rate change of a simulated SPC sensor has no influence on the trigger pulse length measurement.

## Function Syntax

```plaintext
SensorErrorCode sensorSetClockTickLength(char[] sysVarNamespace, double clockTickLengthUs);
```

## Description

Overwrites the clock tick length of a simulated sensor with the given value.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.
- **clockTickLengthUs**: The overridden clock tick length in microseconds.  
  Valid range: 1.0 – 120.0 µs

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Change the sensor's tick length to 2.5 us
result = sensorSetClockTickLength("SENSOR::SENT::SENSORSIM::Sensor", 2.5);

if (result == eSensorNoError)
{
  write("Sensor clock tick length changed successfully.");
}
else
{
  write("Changing sensor clock tick length failed with code: %d", result);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
