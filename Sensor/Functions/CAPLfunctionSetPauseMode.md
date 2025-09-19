[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSetPauseMode.md)

**CAPL Functions** » **Sensor** » **SetPauseMode**

# SetPauseMode

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT. Currently, changing the pause configuration is only supported by SENT channels that are mapped to a VT2710 module.

## Method Syntax

SensorErrorCode sysvarSensorNamespace.SetPauseMode(dword pauseMode, dword pauseOrFrameLenTicks);

## Description

Sets the pause mode and optionally the pause or frame length of a simulated sensor to the given values.

## Parameters

- **pauseMode**  
  The pause mode to select
  - 0: No pause
  - 1: Fixed pause length
  - 2: Fixed frame length

- **pauseOrFrameLenTicks**  
  Depending on the selected mode, the parameter specifies the length of the pause pulse or the frame in ticks. If no pause is selected the parameter is ignored.  
  Parameter range:
  - Fixed pause mode: 12 – 768 ticks
  - Fixed frame mode: 282 – 922 ticks

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
enum sensorErrorCode result;

// Configure a fixed frame length of 282 ticks for the simulated sensor
result = sysvar::SENSOR::SENT::SENSORSIM::Sensor.SetPauseMode(2, 282);

if (result == eSensorNoError)
{
  write("Changing sensor pause mode succeeded.");
}
else
{
  write("Changing sensor pause mode failed with code: %d", result);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
