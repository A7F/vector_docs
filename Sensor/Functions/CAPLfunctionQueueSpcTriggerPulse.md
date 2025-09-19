[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionQueueSpcTriggerPulse.md)

**CAPL Functions** » [Sensor](../CAPLfunctionsSensorOverview.md) » QueueSpcTriggerPulse

# QueueSpcTriggerPulse

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variables belonging to the SENSOR::SENT namespace.

## Method Syntax

SensorErrorCode sysvarSensorNamespace.QueueSpcTriggerPulse(dword triggerLengthNs, dword responseSpaceLengthNs, dword periodic);

## Description

Queues a single SPC trigger pulse on the specified ECU channel.

## Parameters

- **triggerLengthNs**: The length of the trigger pulse in nanoseconds.
- **responseSpaceLengthNs**: The length of the sensor's response space in nanoseconds.
- **periodic**: 1 = periodic transmission, otherwise single transmission.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
// Sensor configuration
const double cSensorTickLengthUs = 3.0;
const double cSensorMinTriggerLenTicks = 1.5;
const double cSensorTotalTriggerLenTicks = 13.0;
const dword cSensorNumLowTicks = 5;
const dword cSensorNumDataNibbles = 6;

dword triggerLenNs;
dword responseSpaceLenNs;
double maxSensorResponseTicks;

enum sensorErrorCode result;

// Calculate length of SPC trigger pulse in nanoseconds
triggerLenNs = cSensorTickLengthUs * cSensorMinTriggerLenTicks * 1000;
// Calculate length of the sensor's response space in ticks
maxSensorResponseTicks = cSensorTotalTriggerLenTicks - cSensorMinTriggerLenTicks; // Total trigger time high ticks
maxSensorResponseTicks += 56; // Sync pulse
maxSensorResponseTicks += (cSensorNumDataNibbles + 2) * 27; // Status + data + crc nibbles
maxSensorResponseTicks += cSensorNumLowTicks; // SPC end pulse

// Calculate length of the sensor's response space in nanoseconds
responseSpaceLenNs = maxSensorResponseTicks * cSensorTickLengthUs * 1000;

// Queue a periodic SPC trigger pulse with the calculated lengths
result = sysvar::SENSOR::SENT::ECUSIM.QueueSpcTriggerPulse(triggerLenNs, responseSpaceLenNs, 1);
if (result == eSensorNoError)
{
  write("Queuing of periodic SPC trigger pulse succeeded.");
}
else
{
  write("Queuing of periodic SPC trigger pulse failed with code: %d.", result);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
