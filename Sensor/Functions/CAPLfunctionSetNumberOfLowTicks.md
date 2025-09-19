[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSetNumberOfLowTicks.md)

**CAPL Functions** » **Sensor** » **SetNumberOfLowTicks**

# SetNumberOfLowTicks

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT. Currently, changing the number of low ticks is only supported by SENT channels that are mapped to a VT2710 module.

## Method Syntax

`SensorErrorCode sysvarSensorNamespace.SetNumberOfLowTicks(dword numLowTicks);`

## Description

Sets the number of low ticks of a simulated sensor to the given value.

## Parameters

- **numLowTicks**: The number of low ticks.  
  Valid range: 1 – 11 ticks

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Change the sensor's number of low ticks to 7
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.SetNumberOfLowTicks(7);

if (result == eSensorNoError)
{
  write("Changing sensor low ticks succeeded.");
}
else
{
  write("Changing sensor low ticks failed with code: %d", result);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
