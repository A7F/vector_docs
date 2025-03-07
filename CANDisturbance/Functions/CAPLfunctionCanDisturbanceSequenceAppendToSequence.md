[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANDisturbance/Functions/CAPLfunctionCanDisturbanceSequenceAppendToSequence.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN Disturbance Interface](../CAPLfunctionsCANDisturbanceOverview.md) » canDisturbanceSequence::AppendToSequence

# canDisturbanceSequence::AppendToSequence

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

```plaintext
void canDisturbanceSequence::AppendToSequence(word segmentLength, char segmentValue);
```

## Description

Adds a segment to a sequence. If the maximum number of segments is reached, the function always returns 0.

Maximum number of segments: 4096

## Parameters

- **segmentLength**: The segment length in FPGA ticks
- **segmentValue**: The segment value. Possible values:
  - **d**: Dominant level
  - **r**: Recessive level (dominant level is not disturbed on bus)
  - **R**: Recessive stress level (dominant level is disturbed on bus)

## Return Values

- **1**: Segment is added to the sequence
- **0**: Segment is not added to the sequence

## Example

- [canDisturbanceTriggerEnable (Frame and Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#FrameSequence)
- [canDisturbanceTriggerEnable (Multiple Frames and Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#MultipleFrameSequence)
- [canDisturbanceTriggerEnable (External Trigger and Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#ExternalTriggerSequence)
- [canDisturbanceTriggerEnable (Error Frame and Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#ErrorFrameSequence)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)