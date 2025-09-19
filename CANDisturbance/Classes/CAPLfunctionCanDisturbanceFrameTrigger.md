# Class: CanDisturbanceFrameTrigger

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANDisturbance/Classes/CAPLfunctionCanDisturbanceFrameTrigger.md)

**CAPL Functions** » **CAN Disturbance Interface** » **Classes »** Class: CanDisturbanceFrameTrigger

**Valid for**: CANoe DE

## Trigger Configuration: Field Description

With a trigger field, it is possible to define which value each bit of each field in a CAN frame must have to fulfill the trigger condition. When the trigger condition is fulfilled, the CAN Disturbance Interface outputs the configured sequence to the bus.

### Possible values for a bit of a field

- **0**: The bit must be dominant
- **1**: The bit must be recessive
- **-1**: The bit may be dominant or recessive (irrelevant)

Each field of a CAN/CAN FD frame contains one or multiple bits that can be configured. If a field has multiple bits, this field is represented by an array in this data type. The bit order of a field with several bits corresponds to the CAN/CAN FD specification.

For example, the Base Identifier field contains 11 bits, and the field is represented by the attribute **IDBase** of this structure.

The bit represented by **ID28** is the first bit that is sent in the **Base Identifier** field on the bus. To set a defined value for this bit the attribute **IDBase** must be designated **IDBase[10]**.

This means the Array-Index 0 is the **Least Significant Bit** (LSB) and the Array-Index 10 is the **Most Significant Bit** (MSB) in the **Base Identifier** field.

### Methods

- [SetMessage](../Functions/CAPLfunctionCanDisturbanceFrameTriggerSetMessage.md)
- [RecalculateCRC](../Functions/CAPLfunctionCanDisturbanceFrameTriggerRecalculateCRC.md)

### Attributes

You can access control information of a **CanDisturbanceFrameTrigger** object with the following attributes:

- **TriggerFieldType**: The CAN frame field will cause the trigger to start sending the configured sequence. The [system variable](../../../CANoeCANalyzer/Interfaces/CANDisturbance/SysVarDisturbance.md) `sysvar::CanDisturbanceInterace::Enums::FieldType` contains an enumeration of possible values. Type: `dword`
- **TriggerFieldOffset**: The offset in the CAN frame field is configured by **TriggerFieldType**. Type: `dword`
- **IDBase**: The standard ID or extended ID (28-18). Type: `char[11]`
- **RemoteBase**: RTR bit: standard CAN frame, RRS bit: standard CAN FD frame, SRR bit: extended CAN/CAN FD frame. Type: `char`
- **IDE**: The IDE bit in a CAN/CAN FD frame. Type: `char`
- **IDExtended**: The extended ID (17-0) of an extended CAN/CAN FD frame. Type: `char[18]`
- **RemoteExtended**: RTR bit: extended CAN frame, RRS bit: extended CAN FD frame. Type: `char`
- **FDF**: The FDF bit. Type: `char`
- **Reserved**: Res bit: standard and extended CAN FD frame, R0 bit: extended CAN frame. Type: `char`
- **BRS**: The BRS bit for standard and extended CAN FD frame (not usable for CAN frames). Type: `char`
- **ESI**: The ESI bit for standard and extended CAN FD frames (not usable for CAN frames). Type: `char`
- **DLC**: The Data Length Code (DLC) for CAN/CAN FD frames. Type: `char[4]`
- **Payload**: The payload data of a CAN/CAN FD frame. CAN frames up to 64 bits possible, CAN FD frames up to 512 bits possible. Type: `char[512]`
- **StuffCount**: The stuff count field for CAN FD frames. Includes the parity bit. (not usable for CAN frames). Type: `char[4]`
- **CRC**: The CRC value of CAN/CAN FD frames. CAN frames up to 15 bits, CAN FD frames DLC < 10 up to 17 bits, CAN FD Frames DLC >= 10 up to 21 bits. Type: `char[21]`
- **CRCDelimiter**: The CRC delimiter for CAN / CAN FD frames. Type: `char`
- **AckSlot**: The acknowledge slot. Type: `char`
- **AckDelimiter**: The acknowledge delimiter. Type: `char`
- **EndOfFrame**: The End Of Frame (EOF). Type: `char[7]`
