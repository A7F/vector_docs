[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANDisturbance/Classes/CAPLfunctionCanDisturbanceBitSequence.md)

## CAPL Functions » CAN Disturbance Interface » Classes » Class: CanDisturbanceBitSequence

### Class: CanDisturbanceBitSequence

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

Each object of **CanDisturbanceBitSequence** represents one bit within a [CanDisturbanceFrameSequenceField](CAPLfunctionCanDisturbanceFrameSequenceField.md).

### Methods

—

### Attributes

You can access control information of a **CanDisturbanceBitSequence** object with the following attributes:

- **SegmentCount**
  - Description: The number of segments for the bit.
  - Type: dword
  - Access Limitations: —

- **SegmentValue**
  - Description: The value of each segment
  - Possible values:
    - d: dominant level
    - r: recessive level
    - R: recessive stress level
  - Type: char[8]
  - Access Limitations: —

- **SegmentLength**
  - Description: The length of each segment in FPGA ticks.
  - Type: word[8]
  - Access Limitations: —

[Digital Disturbance](../../../CANoeCANalyzer/Interfaces/CANDisturbance/DigitalDisturbance.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
