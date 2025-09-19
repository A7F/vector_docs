# Class: CanDisturbanceExternalTrigger

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

This trigger can be used, if a sequence or a frame based sequence should be sent based on a digital input value.

## Methods

—

## Attributes

You can access control information of a **CanDisturbanceExternalTrigger** object with the following attributes:

- **DIOChannel**
  - Description: Number of the DIO channel.
  - Possible values:
    - 0: DIN0
    - 1: DIN1
  - Type: dword
  - Access Limitations: —

- **TriggerType**
  - Description: The trigger type used for the external trigger.
  - Possible values:
    - 0: Active Low
    - 1: Active High
    - 2: Rising Edge
    - 3: Falling Edge
  - Type: dword
  - Access Limitations: —
