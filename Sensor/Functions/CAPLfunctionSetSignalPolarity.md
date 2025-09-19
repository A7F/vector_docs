[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSetSignalPolarity.md)

**CAPL Functions** » **Sensor** » **SetSignalPolarity**

# SetSignalPolarity

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT. Currently, changing the signal polarity at measurement time is only supported by SENT channels that are mapped to a VT2710 module.

## Method Syntax

SensorErrorCode sysvarSensorNamespace.SetSignalPolarity(dword inverted);

## Description

Sets the signal polarity of a simulated sensor to the given value.

## Parameters

- **inverted**  
  The signal polarity.
  - 0: Default
  - 1: Inverted

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Set the sensor's signal polarity to inverted
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.SetSignalPolarity(1);

if (result == eSensorNoError)
{
  write("Setting the signal polarity succeeded.");
}
else
{
  write("Setting the signal polarity failed with code: %d", result);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
