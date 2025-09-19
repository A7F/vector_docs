# canDisturbanceFrameSequence::SetMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `void canDisturbanceFrameSequence::SetMessage(dword deviceID, message msg);` //form 1
- `void canDisturbanceFrameSequence::SetMessage(dword deviceID, message msg, word arbitrationTicks, word dataTicks);` //form 2

## Description

Configures the output sequence based on the frame **msg**.

All **CanDisturbanceBitSequence** objects in all fields of this frame sequence are overridden by a sequence that corresponds to the bits the frame.

## Parameters

- **deviceID**: The device ID of the CAN Disturbance Interface.
- **msg**: The frame data that should be used for the frame sequence.
- **arbitrationTicks**: Defines the ticks used for one bit in the arbitration phase.

  **Note**: If form 1 is used or set to 0, the arbitration ticks are calculated using the channel bit timings of the CAN Disturbance Interface.

- **dataTicks**: Defines the ticks used for one bit in the data phase.

  **Note**: If form 1 is used or set to 0, the arbitration ticks are calculated using the channel bit timings of the CAN Disturbance Interface.

## Return Values

—

## Example

- [canDisturbanceTriggerEnable (Frame and Frame Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#FrameFrameSequence)
- [canDisturbanceTriggerEnable (Multiple Frames and Frame Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#MultipleFrameFrameSequence)
- [canDisturbanceTriggerEnable (External Trigger and Frame Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#ExternalTriggerFrameSequence)
- [canDisturbanceTriggerEnable (Error Frame and Frame Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#ErrorFrameFrameSequence)
