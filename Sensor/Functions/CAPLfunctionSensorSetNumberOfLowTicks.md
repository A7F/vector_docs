[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorSetNumberOfLowTicks.md)

**CAPL Functions** » **Sensor** » **sensorSetNumberOfLowTicks**

# sensorSetNumberOfLowTicks

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
Currently, changing the number of low ticks is only supported by SENT channels that are mapped to a **VT2710** module.

## Function Syntax

```plaintext
SensorErrorCode sensorSetNumberOfLowTicks(char[] sysVarNamespace, dword numLowTicks);
```

## Description

Sets the number of low ticks of a simulated sensor to the given value.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.
- **numLowTicks**: The number of low ticks.  
  Valid range: 1 – 11 ticks

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Change the sensor's number of low ticks to 7
result = sensorSetNumberOfLowTicks("SENSOR::SENT::SENSORSIM::Sensor", 7);

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
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)