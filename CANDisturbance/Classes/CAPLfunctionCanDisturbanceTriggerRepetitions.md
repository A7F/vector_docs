[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANDisturbance/Classes/CAPLfunctionCanDisturbanceTriggerRepetitions.md)

## CAPL Functions » CAN Disturbance Interface » Classes » Class: CanDisturbanceTriggerRepetitions

### Class: CanDisturbanceTriggerRepetitions

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

The repetition of a defined trigger can be configured with this class.

The repetitions are configurable via a cycle and repetitions within a cycle. It is also possible to define a hold-off time between cycles and repetitions.

### Methods

—

### Attributes

You can access control information of a **CanDisturbanceTriggerRepetitions** object with the following attributes:

- **Cycles**
  - Description: Number of cycles by which the trigger conditions should be repeated. A value of 0 means infinitely.
  - Possible values: 0 - 1023
  - Type: dword
  - Access Limitations: —

- **HoldOffCycles**
  - Description: Defines the time in milliseconds between two cycles during which the trigger condition is not raised.
  - Possible values: 0 - 65535
  - Type: dword
  - Access Limitations: —

- **Repetitions**
  - Description: Number of repetitions after which the trigger condition should be activated again. A value of 0 means infinitely.
  - Possible values: 0 - 1023. The value 0 means infinite repetitions.
  - Type: dword
  - Access Limitations: —

- **HoldOffRepetitions**
  - Description: Defines the time in milliseconds between two repetitions during which the trigger condition is not raised.
  - Possible values: 0 - 65535
  - Type: dword
  - Access Limitations: —

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)