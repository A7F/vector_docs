# canDisturbanceFrameTrigger::SetMessage

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

```plaintext
long canDisturbanceFrameTrigger::SetMessage(message msg, dword deviceID, dword validityMask);
```

## Description

Sets the frame for the trigger condition. The mask is filled automatically with the data of the frame. The used data can be configured with the validity mask.

## Parameters

- **msg**: The frame data that should be used for the frame trigger.
- **deviceID**: The device ID of the CAN Disturbance Interface.
- **validityMask**: The `validityMask` is a bit field that defines which fields of the frame object should be significant for the frame trigger configuration. All other fields are not relevant for matching frames and are therefore irrelevant.

  The possible values can be accessed with the [system variable](../../../CANoeCANalyzer/Interfaces/CANDisturbance/SysVarDisturbance.md)`sysvar::CanDisturbance::Enums::ValidityMaskFlags`. If more than one field is to be used, the values of this system variable can be combined with a logical OR.

  - **Bit 0**: IDBase - ID28-18
  - **Bit 1**: IDExtended - ID17-0
  - **Bit 2**: RemoteBase - RTR
  - **Bit 3**: IDE - IDE
  - **Bit 4**: RemoteExt - RRS
  - **Bit 5**: FDF - FDF
  - **Bit 6**: Reserved - res
  - **Bit 7**: BRS - BRS
  - **Bit 8**: ESI - ESI
  - **Bit 9**: DLC - DLC0-DLC3
  - **Bit 10**: Data - D0-D63
  - **Bit 11**: StuffCount - StuffCount
  - **Bit 12**: CRC - CRC (length depends on format and on DLC)
  - **Bit 13**: CRCDelimiter - CRCdel
  - **Bit 14**: ACKSlot - ACK
  - **Bit 15**: ACKDelimiter - ACKdel
  - **Bit 16**: EndOfFrame - EOF

  *CBFF - Classical Base Frame Format  
  *CEFF - Classical Extended Frame Format  
  *FBFF - FD Base Frame Format  
  *FEFF – FD Extended Frame Format  

## Return Values

- **1**: Success
- **0**: Error

## Example

- [canDisturbanceTriggerEnable (Frame and Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#FrameSequence)
- [canDisturbanceTriggerEnable (Frame and Frame Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#FrameFrameSequence)
- [canDisturbanceTriggerEnable (Multiple Frames and Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#MultipleFrameSequence)
- [canDisturbanceTriggerEnable (Multiple Frames and Frame Sequence)](CAPLfunctionCanDisturbanceTriggerEnable.md#MultipleFrameFrameSequence)
