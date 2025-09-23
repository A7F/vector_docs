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
