# ResetCustomCRCCalculation

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT.

## Function Syntax

```plaintext
SensorErrorCode sysvarSensorNamespace.ResetCustomCRCCalculation();
```

## Description

Resets custom CRC algorithm callback.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;
// Reset custom crc calculation algorithm
result = sysvar::SENSOR::SENT::SensorSim::Sensor.ResetCustomCRCCalculation();
if (result == eSensorNoError)
{
  write("Resetting custom crc algorithm succeeded.");
}
else
{
  write("Resetting custom crc algorithm failed with code: %d", result);
}
```
