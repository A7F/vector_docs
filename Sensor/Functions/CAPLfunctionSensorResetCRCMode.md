[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorResetCRCMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorResetCRCMode

# sensorResetCRCMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
SensorErrorCode sensorResetCRCMode(char[] sysVarNamespace);
```

## Description

Resets the CRC mode of a sensor to the initially configured value. If short serial messages are selected, this function also resets the CRC algorithm used to calculate the serial message checksum.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Reset the sensor's pause mode
result = sensorResetCRCMode("SENSOR::SENT::SENSORSIM::Sensor");

if (result == eSensorNoError)
{
    write("Resetting sensor CRC mode succeeded.");
}
else
{
    write("Resetting sensor CRC mode failed with code: %d", result);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)