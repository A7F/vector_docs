# canDisturbanceCombinedFrameTrigger::AddFrameTrigger

[CAPL Functions](../../CAPLfunctions.md) » [CAN Disturbance Interface](../CAPLfunctionsCANDisturbanceOverview.md) » canDisturbanceCombinedFrameTrigger::AddFrameTrigger

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
long canDisturbanceCombinedFrameTrigger::AddFrameTrigger(CanDisturbanceFrameTrigger frameTrigger);
```

## Description

Adds a frame trigger to the combined frame trigger. Up to 32 frame triggers can be added to a combined frame trigger.

## Parameters

- **frameTrigger**: The frame trigger to be added to the combined frame trigger.

## Return Values

- **1**: Frame trigger has been added.
- **0**: Frame trigger has not been added.

## Example

- [canDisturbanceTriggerEnable (Multiple Frames and Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#MultipleFrameSequence)
- [canDisturbanceTriggerEnable (Multiple Frames and Frame Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#MultipleFrameFrameSequence)
