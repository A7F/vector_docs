# sensorSetSignalPolarity

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorSetSignalPolarity.md)

**CAPL Functions** » **Sensor** » sensorSetSignalPolarity

## Valid for: CANoe DE • CANoe4SW DE

**Note:** Currently, changing signal polarity at measurement time is only supported by SENT channels that are mapped to a VT2710 module.

## Function Syntax

```
SensorErrorCode sensorSetSignalPolarity(char[] sysVarNamespace, dword inverted);
```

## Description

Sets the signal polarity of a simulated sensor to the given value.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.
- **inverted**: The signal polarity.
  - 0: Default
  - 1: Inverted

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;
// Set the sensor's signal polarity to inverted
result = sensorSetSignalPolarity("SENSOR::SENT::SENSORSIM::Sensor", 1);

if (result == eSensorNoError)
{
  write("Setting the signal polarity succeeded.");
}
else
{
  write("Setting the signal polarity failed with code: %d", result);
}
```
