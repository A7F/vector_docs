[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionStopSpcTriggerPulseTransmission.md)

**CAPL Functions** » **Sensor** » **StopSpcTriggerPulseTransmission**

# StopSpcTriggerPulseTransmission

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variables belonging to the SENSOR::SENT namespace.

## Method Syntax

`SensorErrorCode sysvarSensorNamespace.StopSpcTriggerPulseTransmission();`

## Description

Stops any periodic trigger pulse transmission on the specified ECU channel.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;

// Stop periodic SPC trigger pulse transmission
result = sysvar::SENSOR::SENT::ECUSIM.StopSpcTriggerPulseTransmission();

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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)