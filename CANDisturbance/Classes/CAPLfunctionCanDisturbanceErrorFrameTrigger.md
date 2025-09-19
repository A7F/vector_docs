# Class: CanDisturbanceErrorFrameTrigger

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

This trigger can be used to trigger on an active error flag or the error flag delimiter of an error frame. The error frame phase can be configured by a flag field.

## Methods

—

## Attributes

You can access control information of a **CanDisturbanceErrorFrameTrigger** object with the following attributes:

- **Keyword**: ErrorFramePhase
  - **Description**: The phase of the error frame.
    - Possible values:
      - 0: Active error flag
      - 1: Error flag delimiter
  - **Type**: dword
  - **Access Limitations**: —

- **Keyword**: Offset
  - **Description**: The offset within the phase.
    - **Note**: If the error frame phase is the active error flag, the minimum value for the offset is 6.
  - **Type**: dword
  - **Access Limitations**: —
