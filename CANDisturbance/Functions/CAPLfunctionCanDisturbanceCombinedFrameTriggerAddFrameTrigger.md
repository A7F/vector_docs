[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANDisturbance/Functions/CAPLfunctionCanDisturbanceCombinedFrameTriggerAddFrameTrigger.md)

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)