# SetSyncPulseTolerance

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT. Currently, changing the sync pulse tolerance is only supported by SENT channels that are mapped to a VT2710 module. This method may only be called in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Method Syntax

SensorErrorCode sysvarSensorNamespace.SetSyncPulseTolerance(dword tolerance);

## Description

Sets the allowed sync pulse tolerance in percent on the specified SENT channel.

## Parameters

- **tolerance**: The tolerance value in percent.  
  Valid range: 1 – 50 % (Default value 20%)

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
on preStart
{
  enum SensorErrorCode result;

  // Set ECU channel sync pulse tolerance to 40%
  result = sysvar::SENSOR::SENT::ECUSIM.SetSyncPulseTolerance(40);

  if (result == eSensorNoError)
  {
    write("Changing sync pulse tolerance succeeded.");
  }
  else
  {
    write("Changing sync pulse tolerance failed with code: %d", result);
  }
}
```
