[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionQueueMosiData.md)

**CAPL Functions** » **Sensor** » **QueueMosiData**

# QueueMosiData

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of SPI slaves.

## Method Syntax

```plaintext
SensorErrorCode SysVarNamespace.QueueMosiData(byte buffer[], dword bitCount); // from 1
SensorErrorCode SysVarNamespace.QueueMosiData(byte buffer [], dword bitCount, dword delayNs); // from 2
```

## Description

This method is intended to be used for SPI master simulation. It inserts the given MOSI data into the send queue from the master to the given slave.

## Parameters

- **buffer**: The array of bytes that shall be put into the master's send queue. The bytes of the array will be output in the order they are specified. The bits of the bytes will be output MSB first.

  **Example:**  
  The byte array `{ 0xD1, 0x3B }` will be output as `11010001 00111011`.

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
sysvar::SENSOR::SPI::ExampleChannel::ExampleSlave.QueueMosiData(requestData, 12);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
