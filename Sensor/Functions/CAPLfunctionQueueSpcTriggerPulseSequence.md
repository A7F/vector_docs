# QueueSpcTriggerPulseSequence

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variables belonging to the SENSOR::SENT namespace.

## Method Syntax

SensorErrorCode sysvarSensorNamespace.QueueSpcTriggerPulseSequence (dword[] triggerLengthsNs, dword[] responseSpaceLengthsNs, dword sequenceLength, dword periodic);

## Description

Queues a sequence of SPC trigger pulses on the specified ECU channel.

## Parameters

- **triggerLengthNs**: Array of trigger pulse lengths in nanoseconds.
- **responseSpaceLengthNs**: Array of sensor response space lengths in nanoseconds.
- **sequenceLength**: The length of the trigger pulse sequence.
- **periodic**: 1 = periodic transmission, otherwise single transmission.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
// Sensor configurations
const dword cNumSpcSensors = 2;
double cSensorTickLengthUs[cNumSpcSensors] = { 3.0, 3.0 };
double cSensorMinTriggerLenTicks[cNumSpcSensors] = { 1.5, 5.0 };
double cSensorTotalTriggerLenTicks[cNumSpcSensors] = { 13.0, 13.0 };
dword cSensorNumLowTicks[cNumSpcSensors] = { 5, 5 };
dword cSensorNumDataNibbles[cNumSpcSensors] = { 6, 4 };

dword i;
dword triggerLensNs[cNumSpcSensors];
dword responseSpaceLensNs[cNumSpcSensors];

enum sensorErrorCode result;

for (i = 0; i < cNumSpcSensors; i++)
{
  double maxSensorResponseTicks;

  // Calculate length of SPC trigger pulse in nanoseconds
  triggerLensNs[i] = cSensorTickLengthUs[i] * cSensorMinTriggerLenTicks[i] * 1000;

  // Calculate length of the sensor's response space in ticks
  maxSensorResponseTicks = cSensorTotalTriggerLenTicks[i] - cSensorMinTriggerLenTicks[i]; // Total trigger time high ticks
  maxSensorResponseTicks += 56; // Sync pulse
  maxSensorResponseTicks += (cSensorNumDataNibbles[i] + 2) * 27; // Status + data + crc nibbles
  maxSensorResponseTicks += cSensorNumLowTicks[i]; // SPC end pulse

  // Calculate length of the sensor's response space in nanoseconds
  responseSpaceLensNs[i] = maxSensorResponseTicks * cSensorTickLengthUs[i] * 1000;
}

// Queue a periodic SPC trigger pulse sequence with the calculated lengths
result = sysvar::SENSOR::SENT::ECUSIM.QueueSpcTriggerPulseSequence(triggerLensNs, responseSpaceLensNs, cNumSpcSensors, 1);
if (result == eSensorNoError)
{
  write("Queuing of periodic SPC trigger pulse sequence succeeded.");
}
else
{
  write("Queuing of periodic SPC trigger pulse sequence failed with code: %d.", result);
}
```
