[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorSwitchSupplyVoltage.md)

**CAPL Functions** » **Sensor** » **sensorSwitchSupplyVoltage**

# sensorSwitchSupplyVoltage

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorSwitchSupplyVoltage(char[] sysVarNamespace, dword onOff);
```

## Description

Enables or disables the sensor supply voltage of a simulated ECU.

## Parameters

- **sysVarNamespace**: The namespace of the channel or ECU.
- **onOff**:
  - 1 = Supply voltage on
  - 0 = Supply voltage off

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Switch off the supply voltage of a simulated PSI5 ECU
sensorSwitchSupplyVoltage("SENSOR::PSI5::ECUSIM", 0);

// Switch off the supply voltage of a simulated SENT ECU
sensorSwitchSupplyVoltage("SENSOR::SENT::ECUSIM", 0);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)