# Sensor CAPL Functions

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/CAPLfunctionsSensorOverview.md)

**CAPL Functions** » Sensor CAPL Functions

**Valid for**: CANoe DE • CANoe4SW DE

## General

- **QueueSerialMessage / sensorQueueSerialMessage**: Inserts the given serial message into the send queue of the given time slot.
- **QueueValues / sensorQueueValues**: Inserts the given values into the send queue of the given sensor signal system variable.
- **ClearQueue / sensorClearQueue**: Clears the send queue of the given sensor system variable.
- **SwitchSupplyVoltage / sensorSwitchSupplyVoltage**: Enables or disables the sensor supply voltage of a simulated ECU.
- **sensorConvertUnsignedToSigned**: Converts the given n bit input value from unsigned to signed using two's complement.
- **sensorExtractInteger**: Extracts an integer value from the given byte array.
- **sensorInsertInteger**: Inserts the given integer value into the given byte array.
- **sensorReverseBits**: Reverses the given number of bits in the given array.

## I2C Protocol

- **QueueCombinedFrame / sensorQueueCombinedFrame**: Queues a frame to write and then read the given number of bytes from the given slave.
- **QueueFrame / sensorQueueFrame**: Inserts the given data bytes into the response queue of the given slave.
- **QueueReadFrame / sensorQueueReadFrame**: Queues a frame to read the given number of bytes from the given slave.
- **QueueWriteFrame / sensorQueueWriteFrame**: Queues a frame to write the given bytes to the given slave.

## PSI5 Protocol

- **QueuePsi5Frame / sensorQueuePsi5Frame**: Inserts the given frame into the send queue of the given channel.

## SENT Protocol

- **QueueSentFrame / sensorQueueSentFrame**: Inserts the given frame into the send queue of the given channel.
- **ResetClockTickLength / sensorResetClockTickLength**: Resets the clock tick length of a simulated sensor to the initially configured value.
- **ResetCRCMode / sensorResetCRCMode**: Resets the CRC mode of a sensor to the initially configured value.
- **ResetCustomCRCCalculation / sensorResetCustomCRCCalculation**: Resets custom CRC algorithm callback.
- **ResetNumberOfDataNibbles / sensorResetNumberOfDataNibbles**: Resets the number of data nibbles of a simulated sensor to the initially configured value.
- **ResetNumberOfLowTicks / sensorResetNumberOfLowTicks**: Resets the number of low ticks of a simulated sensor to the initially configured value.
- **ResetPauseMode / sensorResetPauseMode**: Resets the pause mode and pause length of a simulated sensor to the initially configured values.
- **ResetSerialMessagingMode / sensorResetSerialMessagingMode**: Resets the serial messaging mode of a sensor to the initially configured value.
- **ResetSignalPolarity / sensorResetSignalPolarity**: Resets the signal polarity of a simulated sensor to the initially configured value.
- **SetClockTickLength / sensorSetClockTickLength**: Overwrites the clock tick length of a simulated sensor with the given value.
- **SetCrcMode / sensorSetCrcMode**: Sets the CRC mode of a sensor to the given value.
- **SetCustomCRCCalculation / sensorSetCustomCRCCalculation**: Set a callback for custom defined CRC calculation algorithm.
- **SetNumberOfDataNibbles / sensorSetNumberOfDataNibbles**: Sets the number of data nibbles of a simulated sensor to the given value.
- **SetNumberOfLowTicks / sensorSetNumberOfLowTicks**: Sets the number of low ticks of a simulated sensor to the given value.
- **SetPauseMode / sensorSetPauseMode**: Sets the pause mode and optionally the pause or frame length of a simulated sensor to the given values.
- **SetSerialMessagingMode / sensorSetSerialMessagingMode**: Sets the serial messaging mode of a sensor to the given value.
- **SetSignalPolarity / sensorSetSignalPolarity**: Sets the signal polarity of a simulated sensor to the given value.
- **SetSyncPulseTolerance / sensorSetSyncPulseTolerance**: Sets the allowed sync pulse tolerance in percent on the specified SENT channel.

## SPC Protocol

- **QueueSpcTriggerPulse / sensorQueueSpcTriggerPulse**: Queues a single SPC trigger pulse on the specified ECU channel.
- **QueueSpcTriggerPulseSequence / sensorQueueSpcTriggerPulseSequence**: Queues a sequence of SPC trigger pulses on the specified ECU channel.
- **StopSpcTriggerPulseTransmission / sensorStopSpcTriggerPulseTransmission**: Stops any periodic trigger pulse transmission on the specified ECU channel.

## SPI Protocol

- **QueueMisoData / sensorQueueMisoData**: SPI slave simulation in basic mode. Inserts the given MISO data into the response queue of the given slave.
- **QueueMosiData / sensorQueueMosiData**: SPI master simulation. Inserts the given MOSI data into the send queue from the master to the given slave.

## UART Protocol

- **QueueSerialFrame / sensorQueueSerialFrame**: Queues one frame for the given datum.
- **QueueSerialFrames / sensorQueueSerialFrames**: Queues one frame for each given datum.

[Option .Sensor](../../CANoeCANalyzer/Sensor/Sensor.md) • [Enumeration](CAPLfunctionsSensorEnumeration.md) • [Structs](CAPLfunctionsSensorStructs.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
