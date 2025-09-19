[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionQueueSentFrame.md)

**CAPL Functions** » **Sensor** » **QueueSentFrame**

# QueueSentFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::SENT.

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

`SensorErrorCode SysVarNamespace.QueueSentFrame(SentSensorFrameStruct frame);`

## Description

Inserts the given frame into the send queue of the given channel.

## Parameters

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
sysvar::SENSOR::SENT::ExampleChannel.QueueSentFrame(frame);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
