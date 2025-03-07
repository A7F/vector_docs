[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorResetPauseMode.md)

# sensorResetPauseMode

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorResetPauseMode

**Valid for:** CANoe DE • CANoe4SW DE

**Note:** Currently, changing the pause mode is only supported by SENT channels that are mapped to a VT2710 module.

## Function Syntax

```plaintext
SensorErrorCode sensorResetPauseMode(char[] sysVarNamespace);
```

## Description

Resets the pause mode and pause length of a simulated sensor to the initially configured values.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Reset the sensor's pause mode
result = sensorResetPauseMode("SENSOR::SENT::SENSORSIM::Sensor");

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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)