[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorClearQueue.md)

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorClearQueue

# sensorClearQueue

Valid for:  CANoe DE •  CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorClearQueue (char[] sysVarNamespace);
```

## Description

Clears the send queue of the given sensor system variable.

## Parameters

- **sysVarNamespace**: The namespace of the channel or sensor whose send queue should be cleared.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Clears the send queue of a simulated PSI5 sensor channel
sensorClearQueue("SENSOR::PSI5::SensorChannel");

// Clears the send queue of a simulated SENT sensor channel
sensorClearQueue("SENSOR::SENT::SensorChannel");

// Clears queued read frames in case of I2C slave simulation or clears
// queued write / combined frames in case of I2C master simulation
sensorClearQueue("SENSOR::I2C::ExampleChannel::Slave1");

// Clears MOSI send queue in case of SPI master simulation or MISO
// send queue in case of SPI slave simulation
sensorClearQueue("SENSOR::SPI::ExampleChannel::Slave1");

// Clears send queue of UART channel
sensorClearQueue("SENSOR::UART::UARTChannel");

// Clears send queue of LVDS channel
sensorClearQueue("SENSOR::LVDS::LVDSChannel");

// Clears send queue of RS485 channel
sensorClearQueue("SENSOR::RS485::RS485Channel");
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)