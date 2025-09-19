[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorStopSpcTriggerPulseTransmission.md)

**CAPL Functions** » **Sensor** » **sensorStopSpcTriggerPulseTransmission**

# sensorStopSpcTriggerPulseTransmission

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorStopSpcTriggerPulseTransmission(char[] sysVarNamespace);
```

## Description

Stops any periodic trigger pulse transmission on the specified ECU channel.

## Parameters

- **sysVarNamespace**: The namespace of the channel or ECU.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Stop periodic SPC trigger pulse transmission
result = sensorStopSpcTriggerPulseTransmission("SENSOR::SENT::ECUSIM");

if (result == eSensorNoError)
{
  write("Stopping of SPC trigger pulse transmission succeeded.");
}
else
{
  write("Stopping of SPC trigger pulse transmission failed with code: %d.", result);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
