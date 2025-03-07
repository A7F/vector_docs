[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSwitchSupplyVoltage.md)

**CAPL Functions** » **Sensor** » **SwitchSupplyVoltage**

# SwitchSupplyVoltage

**Valid for**: CANoe DE • CANoe4SW DE

**Note**

- [PSI5 Protocol](../../../CANoeCANalyzer/Sensor/SensorPSI5Protocol.md)
  - This method can only be called on system variable namespaces of time slots belonging to the namespace **SENSOR::PSI5**.
- [SENT Protocol](../../../CANoeCANalyzer/Sensor/SensorSENTProtocol.md)
  - This method can only be called on system variable namespaces of channels belonging to the namespace **SENSOR::SENT**.

## Method Syntax

SensorErrorCode SysVarNamespace.SwitchSupplyVoltage(dword onOff);

## Description

Enables or disables the sensor supply voltage of a simulated ECU.

## Parameters

- **onOff**
  - 1 = Supply voltage on
  - 0 = Supply voltage off

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Switch off the supply voltage of a simulated PSI5 ECU
sysvar::SENSOR::PSI5::ECUSIM.SwitchSupplyVoltage(0);

// Switch off the supply voltage of a simulated SENT ECU
sysvar::SENSOR::SENT::ECUSIM.SwitchSupplyVoltage(0);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)