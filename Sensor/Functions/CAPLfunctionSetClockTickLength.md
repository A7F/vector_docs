[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSetClockTickLength.md)

**CAPL Functions** » **Sensor** » **SetClockTickLength**

# SetClockTickLength

**Valid for**: CANoe DE • CANoe4SW DE

**Note**

- This method can only be called on system variables belonging to the SENSOR::SENT namespace.
- Currently, changing the tick rate at measurement time is only supported by SENT channels that are mapped to a VT2710 module.
- The tick rate change of a simulated SPC sensor has no influence on the trigger pulse length measurement.

## Method Syntax

`SensorErrorCode sysvarSensorNamespace.SetClockTickLength(double clockTickLengthUs);`

## Description

Overwrites the clock tick length of a simulated sensor with the given value.

## Parameters

- **clockTickLengthUs**: The overridden clock tick length in microseconds.  
  Valid range: 1.4 – 120 µs

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Change the sensor's tick length to 2.5 us
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.SetClockTickLength(2.5);

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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
