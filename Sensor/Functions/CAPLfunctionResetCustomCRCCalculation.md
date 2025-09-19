[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionResetCustomCRCCalculation.md)

**CAPL Functions** » [Sensor](../CAPLfunctionsSensorOverview.md) » ResetCustomCRCCalculation

# ResetCustomCRCCalculation

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT.

## Function Syntax

```plaintext
SensorErrorCode sysvarSensorNamespace.ResetCustomCRCCalculation();
```

## Description

Resets custom CRC algorithm callback.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
enum sensorErrorCode result;
// Reset custom crc calculation algorithm
result = sysvar::SENSOR::SENT::SensorSim::Sensor.ResetCustomCRCCalculation();
if (result == eSensorNoError)
{
  write("Resetting custom crc algorithm succeeded.");
}
else
{
  write("Resetting custom crc algorithm failed with code: %d", result);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
