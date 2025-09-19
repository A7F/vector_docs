# sensorInsertInteger

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorInsertInteger.md)

**CAPL Functions** » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorInsertInteger

## Function Syntax

```plaintext
SensorErrorCode sensorInsertInteger(byte targetBuffer[], dword bufferByteCount, dword signalValue, dword bitOffset, dword bitCount, dword msbFirst);
```

## Description

Inserts the given integer value into the given byte array.

## Parameters

- **targetBuffer**: The array in which the given value shall be inserted.
- **bufferByteCount**: The length of the target array in bytes.
- **signalValue**: The value that shall be inserted into the array.
- **bitOffset**: The offset in bits at which the integer value shall be inserted into the byte array.
- **bitCount**: The length of the value in bits (max. 32 is allowed).
- **msbFirst**: This parameter controls in which order the bits of the value are inserted into the array. 1: the bits will be inserted from MSB to LSB. 0: the bits will be inserted from LSB to MSB.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Byte array used to prepare send data
byte sendData[2] = {0x00, 0x00};

// Insert an 6 bit integer with value 53, 4 bits offset and LSB first
sensorInsertInteger(sendData, 2, 53, 4, 6, 0);

// sendData is now {0x0A, 0xC0 }

// Send the data via SPI
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
