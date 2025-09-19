[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorResetSerialMessagingMode.md)

**CAPL Functions** » **Sensor** » **sensorResetSerialMessagingMode**

# sensorResetSerialMessagingMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
SensorErrorCode sensorResetSerialMessagingMode(char[] sysVarNamespace);
```

## Description

Resets the serial messaging mode of a sensor to the initially configured value.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Reset the sensor's serial messaging mode
result = sensorResetSerialMessagingMode("SENSOR::SENT::SENSORSIM::Sensor");

if (result == eSensorNoError)
{
  write("Resetting sensor serial messaging mode succeeded.");
}
else
{
  write("Resetting sensor serial messaging mode failed with code: %d", result);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
