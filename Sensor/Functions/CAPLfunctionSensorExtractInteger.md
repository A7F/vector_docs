[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorExtractInteger.md)

**CAPL Functions** » [Sensor](../CAPLfunctionsSensorOverview.md) » sensorExtractInteger

# sensorExtractInteger

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword sensorExtractInteger(byte sourceBuffer[], dword bufferByteCount, dword& signalValue, dword bitOffset, dword bitCount, dword msbFirst);
```

## Description

Extracts an integer value from the given byte array.

## Parameters

- **sourceBuffer**: The array from which the given value shall be extracted.
- **bufferByteCount**: The length of the source array in bytes.
- **signalValue**: The variable the extracted signal value will be written to.
- **bitOffset**: The offset in bits at which the integer value shall be extracted from the byte array.
- **bitCount**: The length of the value in bits (max. 32 is allowed).
- **msbFirst**: This parameter controls in which order the bits are extracted from the array. 1: the bits will be extracted from MSB to LSB. 0: the bits will be extracted from LSB to MSB.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```c
dword value;

// This data could have been received via SPI
byte receivedData[2] = {0xE9, 0x40};

// Extract a 10 bit value from the data (offset 0, MSB first)
sensorExtractInteger(receivedData, 2, value, 0, 10, 1);

// value is now 933
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
