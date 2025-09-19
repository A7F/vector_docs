# CAN Message Selectors

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Selectors

You can access control information of the [CAN message object](../../Shared/CAPL/General/DeclarationOfMessages.md) using the following selectors:

### Identification

- **CAN**: Transmission channel or channel through which the frame has been received. Value range: 1..32. Type: word. Access Limitation: —
- **MsgChannel**: Transmission channel or channel through which the frame has been received. Value range: 1..32. Type: word. Access Limitation: —
- **[ID](Selectors/CAPLSelectorID.md)**: [Message identifier](../../Shared/CAPL/General/DeclarationOfMessages.md). Type: dword. Access Limitation: —
- **name**: (unqualified) symbolic name of the message from the database (since version 7.2). Type: char[]. Access Limitation: read only
- **[DIR](Selectors/CAPLSelectorDIR.md)**: Direction of transmission, event classification; possible values: Rx, Tx, TXREQUEST. Type: byte. Access Limitation: —
- **[RTR](Selectors/CAPLSelectorRTR.md)**: Remote Transmission Request; possible values: 0 (no RTR), 1 (RTR). Type: byte. Access Limitation: —
- **[TYPE](Selectors/CAPLSelectorTYPE.md)**: Combination of DIR and RTR for an efficient evaluation. (TYPE = (RTR `<<` 8) | DIR). Type: word. Access Limitation: —
- **[DLC](Selectors/CAPLSelectorDLC.md)**: [The data field length](../../Shared/CAPL/General/DataFieldLegth.md) of a message is coded with the DLC (Data Length Code). Value range: 0..2047. Type: byte. Access Limitation: —
- **DataLength**: Data length in bytes. Type: byte. Access Limitation: —

### Message Times and Lengths

- **[TIME_NS](Selectors/CAPLSelectorTIMENS.md)**: Point in time, units: nanoseconds. Type: int64. Access Limitation: read only
- **[TIME](Selectors/CAPLSelectorTIME.md)**: Point in time, units: 10 microseconds. Type: dword. Access Limitation: —
- **SOF**: Start-of-Frame time stamp in ns. Type: int64. Access Limitation: read only
- **FrameLen**: Frame duration in ns. Type: dword. Access Limitation: read only
- **Bitcount**: Number of bits of a CAN/CAN FD message (incl. IFS bits). Type: word. Access Limitation: —

### Data Access

- **Byte(x)**: Message data byte (unsigned 8 bit); possible values for x: 0…63. Type: byte. Access Limitation: —
- **Word(x)**: Message data word (unsigned 16 bit); possible values for x: 0…62. Type: word. Access Limitation: —
- **DWord(x)**: Message data word (unsigned 32 bit); possible values for x: 0…60. Type: dword. Access Limitation: —
- **QWord(x)**: Message data word (unsigned 64 bit); possible values for x: 0…56. Type: qword. Access Limitation: —
- **char(x)**: Message data byte (signed 8 bit); possible values for x: 0…63. Type: char. Access Limitation: —
- **int(x)**: Message data word (signed 16 bit); possible values for x: 0…62. Type: int. Access Limitation: —
- **long(x)**: Message data word (signed 32 bit); possible values for x: 0…60. Type: long. Access Limitation: —
- **int64(x)**: Message data word (signed 64 bit); possible values for x: 0…56. Type: int64. Access Limitation: —
- **float(x)**: Message data interpreted as IEEE float (32 bit); possible values for x: 0…60. Type: double. Access Limitation: —
- **double(x)**: Message data interpreted as IEEE double (64 bit); possible values for x: 0…56. Type: double. Access Limitation: —

### Flags

- **MsgFlags**: Transmit and receive flags. If more than one flag is set, then their values will be logically ORed. Type: dword. Access Limitation: read only
- **SIMULATED**: Message has been sent by a simulated CAPL node; possible values: 0 (no), 1 (yes). Type: byte. Access Limitation: —
- **FDF**: FD Format Indicator. Type: char. Access Limitation: —
- **BRS**: Bitrate Switch. Type: char. Access Limitation: —
- **ESI**: Error State Indicator. Type: char. Access Limitation: —
- **XLF**: XL Format Indicator. Type: —. Access Limitation: —
- **SDT**: SDU type. Type: —. Access Limitation: —
- **SEC**: Simple Extended Content. Type: —. Access Limitation: —
- **VCID**: Virtual CAN network ID. Type: —. Access Limitation: —
- **AF**: Acceptance field. Type: —. Access Limitation: —
- **SRR_INV**: Inverted SRR. Type: char. Access Limitation: —
- **R0**: Level of the R0 bit on the bus. Type: char. Access Limitation: read only
- **R1**: Level of the R1 bit on the bus. Type: char. Access Limitation: read only
- **TxFailed**: Value range: 0, 1. Type: char. Access Limitation: read only

### PDU Access

- **GetPDU(n, P)**: Retrieve the PDU with index n in this message. Type: long. Access Limitation: read only
- **IsContainer()**: Returns 1 if at least one AUTOSAR ContainerIPdu is mapped to this message, 0 otherwise. Type: long. Access Limitation: read only
- **PDUCount()**: Returns the number of all PDUs in this message. Type: long. Access Limitation: read only
- **PDUOffset(n)**: Returns the byte offset of the start of the PDU with index n in the payload of the message data. Type: long. Access Limitation: read only

### Other Properties

- **FrameCRC**: Checksum of the message. Type: dword. Access Limitation: read only
- **TxReqCount**: Number of transmission attempts for a message. Type: char. Access Limitation: —
- **TxCountRequired**: Number of required transmission attempts for a message. Type: char. Access Limitation: read only
- **StuffCount**: Contains the stuff count of a CAN FD ISO-message. Type: byte. Access Limitation: read only

## Symbolic Constants

To achieve independence from the actual coding of DIR and RTR the following symbolic constants can be used:

### For DIR

- **Rx**: Message was received (DIR == Rx)
- **Tx**: Message was transmitted (DIR == Tx)
- **TXREQUEST**: Transmission request was set for message (DIR == TXREQUEST)

### For TYPE

- **RXREMOTE**: Remote message was received ((DIR == RX) && RTR)
- **TXREMOTE**: Remote message was transmitted ((DIR == Tx) && RTR)
- **TXREQUESTREMOTE**: Transmission request was set for remote message ((DIR == TXREQUEST) && RTR)
- **RXDATA**: Data message was received ((DIR == Rx) && !RTR)
- **TXDATA**: Data message was transmitted ((DIR == Tx) && !RTR)
- **TXREQUESTDATA**: Transmission request was set for data message ((DIR == TXREQUEST) && !RTR)

[Defining Parameter Groups](../J1939/CAPLfunctionsJ1939DefinePG.md)
