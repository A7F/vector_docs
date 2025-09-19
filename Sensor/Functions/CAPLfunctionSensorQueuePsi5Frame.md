[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorQueuePsi5Frame.md)

**CAPL Functions** » **Sensor** » **sensorQueuePsi5Frame**

# sensorQueuePsi5Frame

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorQueuePsi5Frame(char[] sysVarNamespace, Psi5SensorFrameStruct frame);
```

## Description

Inserts the given frame into the send queue of the given channel.

## Parameters

- **sysVarNamespace**: The namespace of the channel the frame shall be queued in.
- **frame**: Specifies the details of the frame that shall be inserted into the send queue.

## Return Values

Returns a [SensorErrorCode](../CAPLfunctionsSensorEnumeration.md).

## Example

```plaintext
Psi5SensorFrameStruct frame;

// Set bit 1 -> this frame will be the only frame sent in this cycle
frame.Frametype = (1 << 1);

// The frame will be sent 30µs after the sync pulse
frame.StartDelayUs = 30;

// Use automatic CRC calculation
frame.CrcMode = ePsi5AutoCrc;

// Fill the frame with data
frame.StartBits = 0; // Binary 00
frame.StartBitsCount = 2;
frame.DataRegionABits = 250;
frame.DataRegionABitsCount = 10;
frame.CrcBits = 0; // Will be set automatically
frame.CrcBitsCount = 3;

// Queue the frame for sending
sensorQueuePsi5Frame("SENSOR::PSI5::ExampleChannel", frame);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
