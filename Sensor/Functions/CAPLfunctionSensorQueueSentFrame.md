[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionSensorQueueSentFrame.md)

**CAPL Functions** » **Sensor** » **sensorQueueSentFrame**

# sensorQueueSentFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
SensorErrorCode sensorQueueSentFrame(char[] sysVarNamespace, SentSensorFrameStruct frame);
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
SentSensorFrameStruct frame;

// Use automatic CRC calculation
frame.CrcMode = eSentAutoCrc;

// Fill the frame with data
frame.StatusBits = 0;
frame.DataBits = 7;
frame.CrcBits = 0; // Will be set automatically

// Queue the frame for sending
sensorQueueSentFrame("SENSOR::SENT::ExampleChannel", frame);
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
