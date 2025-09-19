[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionResetPauseMode.md)

**CAPL Functions** » **Sensor** » **ResetPauseMode**

# ResetPauseMode

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT. Currently, changing the pause mode is only supported by SENT channels that are mapped to a VT2710 module.

## Method Syntax

SensorErrorCode sysvarSensorNamespace.ResetPauseMode();

## Description

Resets the pause mode and pause length of a simulated sensor to the initially configured values.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Reset the sensor's pause mode
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.ResetPauseMode();

if (result == eSensorNoError)
{
  write("Resetting sensor pause mode succeeded.");
}
else
{
  write("Resetting sensor pause mode failed with code: %d", result);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
