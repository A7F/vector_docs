[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANDisturbance/CAPLfunctionsCANDisturbanceOverview.md)

## CAN Disturbance Interface CAPL Functions

[CAPL Functions](../CAPLfunctions.md) » CAN Disturbance Interface CAPL Functions

**Valid for**: CANoe DE

Only available with [CAN Disturbance Interface](../../CANoeCANalyzer/Interfaces/CANDisturbance/CANDisturbance.md). To configure the CAN Disturbance Interface the following functions and methods are available.

---

### Functions

- **canDisturbanceTriggerEnable**
  - **Trigger**: FrameTrigger
  - **Output**: Sequence
  - **Description**: Configures and enables a frame trigger for the CAN Disturbance Interface and outputs a user-defined sequence.

- **canDisturbanceTriggerEnable**
  - **Trigger**: FrameTrigger
  - **Output**: FrameSequence
  - **Description**: Configures and enables a frame trigger for the CAN Disturbance Interface and outputs a frame as sequence.

- **canDisturbanceTriggerEnable**
  - **Trigger**: MultiFrameTrigger
  - **Output**: Sequence
  - **Description**: Configures and enables up to 32 frame triggers for the CAN Disturbance Interface and outputs a user-defined sequence.

- **canDisturbanceTriggerEnable**
  - **Trigger**: MultiFrameTrigger
  - **Output**: FrameSequence
  - **Description**: Configures and enables up to 32 frame triggers for the CAN Disturbance Interface and outputs a frame as sequence.

- **canDisturbanceTriggerEnable**
  - **Trigger**: ExternalTrigger
  - **Output**: Sequence
  - **Description**: Configures and enables an external trigger for the CAN Disturbance Interface and outputs a user-defined sequence.

- **canDisturbanceTriggerEnable**
  - **Trigger**: ExternalTrigger
  - **Output**: FrameSequence
  - **Description**: Configures and enables an external trigger for the CAN Disturbance Interface and outputs a frame as sequence.

- **canDisturbanceTriggerEnable**
  - **Trigger**: ErrorFrame
  - **Output**: Sequence
  - **Description**: Configures and enables an error frame trigger for the CAN Disturbance Interface and outputs a user-defined sequence.

- **canDisturbanceTriggerEnable**
  - **Trigger**: ErrorFrame
  - **Output**: FrameSequence
  - **Description**: Configures and enables an error frame trigger for the CAN Disturbance Interface and outputs a frame as sequence.

- **canDisturbanceTriggerNow**
  - **Description**: Configures and outputs a sequence directly on the CAN bus.

- **canDisturbanceTriggerDisable**
  - **Description**: Disables a configured trigger.

### Methods

- **canDisturbanceCombinedFrameTrigger::AddFrameTrigger**
  - **Description**: Adds a frame trigger to the combined frame trigger.

- **canDisturbanceCombinedFrameTrigger::Clear**
  - **Description**: Deletes all configured frame triggers.

- **canDisturbanceFrameSequence::RecalculateCRC**
  - **Description**: Recalculates the CRC value based on the configured sequence.

- **canDisturbanceFrameSequence::SetMessage**
  - **Description**: Configures the output sequence based on the frame.

- **canDisturbanceFrameTrigger::RecalculateCRC**
  - **Description**: Recalculates the CRC value if fields of the trigger have been changed.

- **canDisturbanceFrameTrigger::SetMessage**
  - **Description**: Sets the frame for the trigger condition.

- **canDisturbanceSequence::AppendToSequence**
  - **Description**: Adds a segment to a sequence.

- **canDisturbanceSequence::Clear**
  - **Description**: Clears the current sequence.

- **canDisturbanceSequence::ToString**
  - **Description**: Represents the sequence as FPGA tick based string.

[Classes](CAPLfunctionsClassesOverview.md)

---

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
