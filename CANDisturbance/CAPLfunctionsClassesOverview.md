[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANDisturbance/CAPLfunctionsClassesOverview.md)

[CAPL Functions](../CAPLfunctions.md) » [CAN Disturbance Interface](CAPLfunctionsCANDisturbanceOverview.md) » Classes

# Classes

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

## Trigger Configuration

- **[CanDisturbanceFrameTrigger](Classes/CAPLfunctionCanDisturbanceFrameTrigger.md)**: A configurable frame trigger for a CAN/CAN FD frame. Every field of a CAN/CAN FD frame is configurable. The position of the frame trigger is configurable.
- **[CanDisturbanceCombinedFrameTrigger](Classes/CAPLfunctionCanDisturbanceCombinedFrameTrigger.md)**: Combination of up to 32 frame triggers. The position of the trigger can be configured once for all frame triggers.
- **[CanDisturbanceExternalTrigger](Classes/CAPLfunctionCanDisturbanceExternalTrigger.md)**: Configuration options for external trigger inputs.
- **[CanDisturbanceErrorFrameTrigger](Classes/CAPLfunctionCanDisturbanceErrorFrameTrigger.md)**: A configurable trigger condition for CAN/CAN FD error frames.

## Sequences

- **[CanDisturbanceSequence](Classes/CAPLfunctionCanDisturbanceSequence.md)**: A user-defined sequence is sent directly on the bus or can be used in combination with a trigger.
- **[CanDisturbanceBitSequence](Classes/CAPLfunctionCanDisturbanceBitSequence.md)**: A sequence describes a bit sequence within a **CanDisturbanceFrameSequenceField**. With this class, it is possible to define a user-defined sequence within a frame sequence. A typical use case is to insert a glitch within a bit near the sample point or to lengthen or shorten a bit. 8 transitions of levels are possible within a bit. The segment with the array index 0 is sent first on the bus.
- **[CanDisturbanceFrameSequenceField](Classes/CAPLfunctionCanDisturbanceFrameSequenceField.md)**: Contains the bits for a field of a CAN/CAN FD frame. A field can contain one or several bits.
- **[CanDisturbanceFrameSequence](Classes/CAPLfunctionCanDisturbanceFrameSequence.md)**: Represents a CAN/CAN FD frame as sequence. Contains all fields of a CAN/CAN FD frame.

## Repetitions

- **[CanDisturbanceTriggerRepetitions](Classes/CAPLfunctionCanDisturbanceTriggerRepetitions.md)**: Can be used to configure repetitions and cycles for a frame trigger in combination with a sequence or only a sequence.

[Classes in CAPL](../ObjectOrientedProg/CAPLfunctionsOOPClassesObjects.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)