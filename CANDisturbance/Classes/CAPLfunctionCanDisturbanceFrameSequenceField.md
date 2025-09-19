[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANDisturbance/Classes/CAPLfunctionCanDisturbanceFrameSequenceField.md)

## CAPL Functions » CAN Disturbance Interface » Classes » Class: CanDisturbanceFrameSequenceField

[CAPL Functions](../../CAPLfunctions.md) » [CAN Disturbance Interface](../CAPLfunctionsCANDisturbanceOverview.md) » [Classes »](../CAPLfunctionsClassesOverview.md) Class: CanDisturbanceFrameSequenceField

### Class: CanDisturbanceFrameSequenceField

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

Each object of **CanDisturbanceFrameSequenceField** represents one field of a CAN frame in an object of class [CanDisturbanceFrameSequence](CAPLfunctionCanDisturbanceFrameSequence.md).

Each field of a CAN/CAN FD frame contains one or multiple bits. Each bit is represented by an object of the class [CanDisturbanceBitSequence](CAPLfunctionCanDisturbanceBitSequence.md).

If a field has several bits, this field is represented by an array in this data type. The bit order of a field with several bits corresponds to the CAN/CAN FD specification.

For example, the CAN **Base Identifier** field contains 11 bits. This field is represented by the attribute **IDBase** of this structure.

The bit represented by **ID28** is the first bit that is sent in the **Base Identifier** field on the bus. For example, to set a dominant value for the **ID28** bit, the attribute **IDBase** of the [CanDisturbanceFrameSequence](CAPLfunctionCanDisturbanceFrameSequence.md) must be called in the following way:

```plaintext
canDisturbanceFrameSequence seq;
seq.IDBase.BitSequence[10].SegmentValue[0] = 'd';
```

This means the array index 0 is the **Least Significant Bit** (LSB) and the array index 10 is the **Most Significant Bit** (MSB) in the **Base Identifier** field.

The table below shows the definition in a common view (expected payload):

- **Point of View**: Transmission on bus
  - **Bit N**: MSB
  - **Bit 0**: LSB

- **Array index**:
  - **N**
  - **0**

### Methods

—

### Attributes

You can access control information of a **CanDisturbanceFrameSequenceField** object with the following attributes:

- **BitSequence**: Represents the bit sequence used for the field.
  - **Type**: [CanDisturbanceBitSequence](CAPLfunctionCanDisturbanceBitSequence.md) [32]
  - **Access Limitations**: —

- **FieldLength**: Returns the length of the field.
  - **Type**: byte
  - **Access Limitations**: read-only

[Digital Disturbance](../../../CANoeCANalyzer/Interfaces/CANDisturbance/DigitalDisturbance.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
