[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionQueueMisoData.md)

## QueueMisoData

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » QueueMisoData

### Valid for: CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of SPI slaves.

### Method Syntax

SensorErrorCode SysVarNamespace.QueueMisoData(byte buffer[], dword bitCount);

### Description

This method is intended to be used for SPI slave simulation in basic mode. It inserts the given MISO data into the response queue of the given slave.

### Parameters

- **buffer**  
  The array of bytes that shall be put into the slave’s response queue. The bytes of the array will be output in the order they are specified. The bits of the bytes will be output MSB first.

  **Example:**  
  The byte array { 0xD1, 0x3B } will be output as 11010001 00111011.

- **bitCount**  
  The length of the data in bits. Must be at least 2 and at most 2016 bits.

### Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

### Example

```plaintext
// Some example values
dword value1 = 7;
dword value2 = 13;

// Byte array used to prepare the slave's 12 bit response
byte responseData[2] = {0x00, 0x00};

// Insert two 6 bit values
SensorInsertInteger(responseData, 2, value1, 0, 6, 1);
SensorInsertInteger(responseData, 2, value2, 6, 6, 1);

// Queue the response in the slave
sysvar::SENSOR::SPI::ExampleChannel::ExampleSlave.QueueMisoData(responseData, 12);
```
