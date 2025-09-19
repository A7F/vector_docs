# Class: CanDisturbanceCombinedFrameTrigger

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**CanDisturbanceCombinedFrameTrigger** combines up to 32 frame triggers. If the received bus data matches one of the configured [CanDisturbanceFrameTrigger](CAPLfunctionCanDisturbanceFrameTrigger.md) objects, then this combined trigger matches and the configured sequence is output to the bus.

The attributes **TriggerFieldType** and **TriggerFieldOffset** of the added [CanDisturbanceFrameTrigger](CAPLfunctionCanDisturbanceFrameTrigger.md) objects are ignored. Use the attributes **TriggerFieldType** and **TriggerFieldOffset** of the **CanDisturbanceCombinedFrameTrigger** object instead.

## Methods

- [AddFrameTrigger](../Functions/CAPLfunctionCanDisturbanceCombinedFrameTriggerAddFrameTrigger.md)
- [Clear](../Functions/CAPLfunctionCanDisturbanceCombinedFrameTriggerClear.md)

## Attributes

You can access control information of a **CanDisturbanceCombinedFrameTrigger** object with the following attributes:

- **CountOfFrameTrigger**: Number of configured frame triggers. Maximum number: 32. Type: dword. Access Limitations: read-only.
- **TriggerFieldType**: The CAN frame field that will cause the trigger to start sending the configured sequence. The [system variable](../../../CANoeCANalyzer/Interfaces/CANDisturbance/SysVarDisturbance.md) `sysvar::CanDisturbanceInterace::Enums::FieldType` contains an enumeration of possible values. Type: dword.
- **TriggerFieldOffset**: The offset in the CAN frame field configured by **TriggerFieldType**. If the offset is outside the trigger field, the offset is set to the maximum number of bits this field contains. If the trigger field **EndOfFrame** is used, the offset is extended up to 26. The reason is that in this case an IFS or a Bus Idle trigger can also be configured. Type: dword.
