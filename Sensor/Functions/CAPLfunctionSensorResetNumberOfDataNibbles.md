[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorResetNumberOfDataNibbles.md)

**CAPL Functions** » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorResetNumberOfDataNibbles

# sensorResetNumberOfDataNibbles

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Currently, changing the number of data nibbles at measurement time is only supported by SENT channels that are mapped to a VT2710 module.

## Function Syntax

```plaintext
SensorErrorCode sensorResetNumberOfDataNibbles(char[] sysVarNamespace);
```

## Description

Resets the number of data nibbles of a simulated sensor to the initially configured value.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Reset the sensor's number of data nibbles
result = sensorResetNumberOfDataNibbles("SENSOR::SENT::SENSORSIM::Sensor");

if (result == eSensorNoError)
{
  write("Resetting sensor data nibbles succeeded.");
}
else
{
  write("Resetting sensor data nibbles failed with code: %d", result);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
