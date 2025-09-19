[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionClearQueue.md)

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » ClearQueue

# ClearQueue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variables belonging to the SENSOR namespace.

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

`SensorErrorCode SysVarNamespace.ClearQueue();`

## Description

Clears the send queue of the given sensor system variable.

## Parameters

—

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Clears the send queue of a simulated PSI5 sensor channel
sysvar::SENSOR::PSI5::SensorChannel.ClearQueue();

// Clears the send queue of a simulated SENT sensor channel
sysvar::SENSOR::SENT::SensorChannel.ClearQueue();

// Clears queued read frames in case of I2C slave simulation or clears
// queued write / combined frames in case of I2C master simulation
sysvar::SENSOR::I2C::ExampleChannel::Slave1.ClearQueue();

// Clears MOSI send queue in case of SPI master simulation or MISO
// send queue in case of SPI slave simulation
sysvar::SENSOR::SPI::ExampleChannel::Slave1.ClearQueue();

// Clears send queue of UART channel
sysvar::SENSOR::UART::UARTChannel.ClearQueue();

// Clears send queue of LVDS channel
sysvar::SENSOR::LVDS::LVDSChannel.ClearQueue();

// Clears send queue of RS485 channel
sysvar::SENSOR::RS485::RS485Channel.ClearQueue();
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
