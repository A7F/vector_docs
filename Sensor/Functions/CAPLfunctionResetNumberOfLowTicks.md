[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionResetNumberOfLowTicks.md)

**CAPL Functions** » **Sensor** » **ResetNumberOfLowTicks**

# ResetNumberOfLowTicks

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT. Currently, changing the number of low ticks is only supported by SENT channels that are mapped to a VT2710 module.

## Method Syntax

`SensorErrorCode sysvarSensorNamespace.ResetNumberOfLowTicks();`

## Description

Resets the number of low ticks of a simulated sensor to the initially configured value.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Reset the sensor's number of low ticks
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.ResetNumberOfLowTicks();

if (result == eSensorNoError)
{
  write("Resetting sensor low ticks succeeded.");
}
else
{
  write("Resetting sensor low ticks failed with code: %d", result);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
