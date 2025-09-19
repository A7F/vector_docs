[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/Functions/CAPLfunctionQueuePsi5Frame.md)

[CAPL Functions](../../CAPLfunctions.md) » [Sensor](../CAPLfunctionsSensorOverview.md) » QueuePsi5Frame

# QueuePsi5Frame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This method can only be called on system variable namespaces of channels belonging to the namespace SENSOR::PSI5.

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

`SensorErrorCode SysVarNamespace.QueuePsi5Frame(Psi5SensorFrameStruct frame);`

## Description

Inserts the given frame into the send queue of the given channel.

## Parameters

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
sysvar::SENSOR::PSI5::ExampleChannel.QueuePsi5Frame(frame);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
