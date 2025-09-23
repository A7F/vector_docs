[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANDisturbance/Classes/CAPLfunctionCanDisturbanceFrameSequence.md)

## CAPL Functions » CAN Disturbance Interface » Classes » Class: CanDisturbanceFrameSequence

### Class: CanDisturbanceFrameSequence

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

This class represents a frame based sequence for the CAN Disturbance Interface. The frame can be configured by using the SetMessage method or by using the different attributes.

### Methods

- [SetMessage](../Functions/CAPLfunctionCanDisturbanceFrameSequenceSetMessage.md)
- [RecalculateCRC](../Functions/CAPLfunctionCanDisturbanceFrameSequenceRecalculateCRC.md)

### Attributes

You can access control information of a **CanDisturbanceFrameSequence** object with the following attributes:

- **IDBase**: Base ID of a frame
- **RemoteBase**: RTR/SSR or RRS bit
- **IDE**: Extended identifier bit
- **IDExtended**: Extended ID of a frame
- **RemoteExtended**: RTR/RRS
- **FDF**: FDF bit
- **Reserved**: r0/res bit
- **BRS**: Bitrate switch bit
- **ESI**: Error switch identifier bit
- **DLC**: Data length code field
- **Payload**: The payload field
- **StuffCount**: The stuff count includes the parity bit
- **CRC**: Checksum field
- **CRCDelimiter**: CRC delimiter
- **AckSlot**: Acknowledge slot
- **AckDel**: Acknowledge delimiter
- **EOF**: End of frame
- **ArbitrationTicks**: Ticks used by default for one bit of the arbitration phase (read only)
- **DataTicks**: Ticks used by default for one bit of the data phase (read only)

[Digital Disturbance](../../../CANoeCANalyzer/Interfaces/CANDisturbance/DigitalDisturbance.md)
