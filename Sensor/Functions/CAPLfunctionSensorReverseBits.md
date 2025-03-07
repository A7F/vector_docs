# sensorReverseBits

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorReverseBits.md)

**CAPL Functions** » **Sensor** » **sensorReverseBits**

## Valid for

[Feature availability for your product](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorReverseBits(byte buffer[], dword bufferByteCount, dword bitCount);
```

## Description

Reverses the given number of bits in the given array.

## Parameters

- **buffer**: The array in which the bits shall be reversed.
- **bufferByteCount**: The length of the array in bytes.
- **bitCount**: The number of bits in the array that shall be reversed.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
// Byte array containing 10 bits of data in MSB first format
byte sendData[2] = {0xE9, 0x40};

// Convert to LSB first by reversing these 10 bits
sensorReverseBits(sendData, 2, 10);

// sendData is now {0xA5, 0xC0 }

// Send the data via SPI
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)