[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorResetCustomCRCCalculation.md)

## sensorResetCustomCRCCalculation

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorResetCustomCRCCalculation

### Valid for: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
SensorErrorCode sensorResetCustomCRCCalculation(char[] sysVarNamespace);
```

### Description

Resets custom CRC algorithm callback.

### Parameters

- **sysVarNamespace**: The namespace of the sensor.

### Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

### Example

```c
enum sensorErrorCode result;
// Reset custom crc calculation algorithm
result = sensorResetCustomCRCCalculation("SENSOR::SENT::SensorSim::Sensor");
if (result == eSensorNoError)
{
  write("Resetting custom crc algorithm succeeded.");
}
else
{
  write("Resetting custom crc algorithm failed with code: %d", result);
}
```

---

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
