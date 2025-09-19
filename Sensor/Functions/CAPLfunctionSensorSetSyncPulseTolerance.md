[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorSetSyncPulseTolerance.md)

**CAPL Functions** » **Sensor** » **sensorSetSyncPulseTolerance**

# sensorSetSyncPulseTolerance

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
Currently, changing the sync pulse tolerance is only supported by SENT channels that are mapped to a **VT2710** module. This function may only be called in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Function Syntax

```plaintext
SensorErrorCode sensorSetSyncPulseTolerance(char[] sysVarNamespace, dword tolerance);
```

## Description

Sets the allowed sync pulse tolerance in percent on the specified SENT channel.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor.
- **tolerance**: The tolerance value in percent.  
  Valid range: 1 – 50 % (Default value 20%)

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
on preStart
{
  enum SensorErrorCode result;

  // Set Trace channel sync pulse tolerance to 50%
  result = sensorSetSyncPulseTolerance("SENSOR::SENT::TRACE", 50);

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

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
