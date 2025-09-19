# sensorSetCrcMode

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorSetCrcMode.md)

**CAPL Functions** » **Sensor** » **sensorSetCrcMode**

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
SensorErrorCode sensorSetCRCMode(char[] sysVarNamespace, dword crcMode);
```

## Description

Sets the CRC mode of a sensor to the given value.

If short serial messages are selected, this method also changes the CRC algorithm used to calculate the serial message checksum.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.
- **crcMode**: The CRC mode to be set.
  - 3 ([eSentRecommendedCrc](../CAPLfunctionsSensorEnumeration.md)): Recommended CRC mode
  - 4 ([eSentLegacyCrc](../CAPLfunctionsSensorEnumeration.md)): Legacy CRC mode

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Use the legacy algorithm to calculate the sensor checksum
result = sensorSetCRCMode("SENSOR::SENT::SENSORSIM::Sensor", eSentLegacyCrc);

if (result == eSensorNoError)
{
  write("Changing sensor CRC mode succeeded.");
}
else
{
  write("Changing sensor CRC mode failed with code: %d", result);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
