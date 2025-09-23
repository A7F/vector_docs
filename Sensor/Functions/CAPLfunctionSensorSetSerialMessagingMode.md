[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorSetSerialMessagingMode.md)

## CAPL Functions » Sensor » sensorSetSerialMessagingMode

### Valid for: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
SensorErrorCode sensorSetSerialMessagingMode(char[] sysVarNamespace, dword serialMsgMode);
```

### Description

Sets the serial messaging mode of a sensor to the given value.

### Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.
- **serialMsgMode**: The serial messaging mode to be set.
  - 0: Short mode
  - 1: Enhanced mode

### Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

### Example

```plaintext
enum sensorErrorCode result;

// Change the sensor's serial message mode to "Enhanced"
result = sensorSetSerialMessagingMode("SENSOR::SENT::SENSORSIM::Sensor", 1);

if (result == eSensorNoError)
{
  write("Changing sensor serial messaging mode succeeded.");
}
else
{
  write("Changing sensor serial messaging failed with code: %d", result);
}
```
