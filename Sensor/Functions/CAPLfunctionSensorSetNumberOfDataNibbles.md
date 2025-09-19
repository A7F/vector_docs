# sensorSetNumberOfDataNibbles

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorSetNumberOfDataNibbles.md)

**CAPL Functions** » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorSetNumberOfDataNibbles

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
Currently, changing the number of data nibbles at measurement time is only supported by SENT channels that are mapped to a VT2710 module.

## Function Syntax

```plaintext
SensorErrorCode sensorSetNumberOfDataNibbles(char[] sysVarNamespace, dword numDataNibbles);
```

## Description

Sets the number of data nibbles of a simulated sensor to the given value.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.
- **numDataNibbles**: The number of data nibbles.  
  Valid range: 1-6 nibbles

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Change the sensor's number of data nibbles to 4.
result = sensorSetNumberOfDataNibbles("SENSOR::SENT::SENSORSIM::Sensor", 4);

if (result == eSensorNoError)
{
  write("Changing sensor data nibbles succeeded.");
}
else
{
  write("Changing sensor data nibbles failed with code: %d", result);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
