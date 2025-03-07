[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorResetNumberOfLowTicks.md)

**CAPL Functions** » **Sensor** » **sensorResetNumberOfLowTicks**

# sensorResetNumberOfLowTicks

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note:** Currently, changing the number of low ticks is only supported by SENT channels that are mapped to a **VT2710** module.

## Function Syntax

```c
SensorErrorCode sensorResetNumberOfLowTicks(char[] sysVarNamespace);
```

## Description

Resets the number of low ticks of a simulated sensor to the initially configured value.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Reset the sensor's number of low ticks
result = sensorResetNumberOfLowTicks("SENSOR::SENT::SENSORSIM::Sensor");

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

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)