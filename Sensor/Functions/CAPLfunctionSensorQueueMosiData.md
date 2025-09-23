[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorQueueMosiData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorQueueMosiData

# sensorQueueMosiData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorQueueMosiData(char[] sysVarNamespace, byte buffer[], dword bitCount); // from 1
SensorErrorCode sensorQueueMosiData(char[] sysVarNamespace, byte buffer[], dword bitCount, dword delayNs); // from 2
```

## Description

This function is intended to be used for SPI master simulation. It inserts the given MOSI data into the send queue from the master to the given slave.

## Parameters

- **sysVarNamespace**: The namespace of the slave the data shall be queued for.
- **buffer**: The array of bytes that shall be put into the master's send queue. The bytes of the array will be output in the order they are specified. The bits of the bytes will be output MSB first.

  **Example:** The byte array `{ 0xD1, 0x3B }` will be output as `11010001 00111011`.
- **bitCount**: The length of the data in bits. Must be at least 2 and at most 2016 bits.
- **delayNs**: If this parameter is provided, the master will wait the specified amount of time before actually sending the data.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Some example values
dword value1 = 7;
dword value2 = 13;

// Byte array used to prepare the master request
byte requestData[2] = {0x00, 0x00};

// Insert two 6 bit values
SensorInsertInteger(requestData, 2, value1, 0, 6, 1);
SensorInsertInteger(requestData, 2, value2, 6, 6, 1);

// Send the prepared 12 bits to the ExampleSlave
sensorQueueMosiData("SENSOR::SPI::ExampleChannel::ExampleSlave", requestData, 12);
```
