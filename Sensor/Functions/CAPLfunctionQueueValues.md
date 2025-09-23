# QueueValues

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variables representing stimulation signals in the SENSOR namespace.

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

`SensorErrorCode SysVarName.QueueValues (float[] values, dword valueCount);`

## Description

Inserts the given values into the send queue of the given sensor signal system variable.

## Parameters

- **values**: Specifies the values that shall be queued.
- **valueCount**: Specifies the number of values in the given array.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
float values[10];
// Todo: fill array with signal values

sysvar::SENSOR::PSI5::ExampleChannel::ExampleSensor::ExampleTimeslot::Signals::ExampleSignal_Stim.QueueValues( values, 10);
```
