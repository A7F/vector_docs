[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/CAPLfunctionJ1939GroupSelectors.md)

# Parameter Group Selectors

[CAPL Functions](../CAPLfunctions.md) » [J1939](CAPLfunctionsJ1939StartPage.md) » Parameter Group Selectors

**Valid for**: CANoe DE • CANoe4SW DE

## Selectors

You can access control information of the J1939 Parameter Group (PG) object using the following selectors:

### Identification

- **CAN MsgChannel**: Transmission channel or channel through which the frame has been received. Value range: 1..32. Type: word. Access Limitation: —
- **ID**: [CAN Message identifier](../../Shared/CAPL/General/DeclarationOfMessages.md). Type: dword. Access Limitation: —
- **PGN**: Parameter Group Number. Type: byte. Access Limitation: —
- **SA**: Source Address of the parameter group. Type: byte. Access Limitation: —
- **DA / PS**: Both attribute selectors PS (PDU Specific) and DA (Destination Address) access the same field of CAN ID, namely PDU Specific, and provide the following information:
  - PDU1 message: destination address of the parameter group
  - PDU2 message: group extension of the parameter group
  Type: byte. Access Limitation: —
- **DA_TP**: Receiver of the parameter group. Initially it has the same value as selector DA (in case of PDU1 message) or 255 (in case of PDU2 message). DA_TP can be used to transmit a PDU2 message with DLC > 8 to some specific address or to identify the destination address in on pg procedure. Type: byte. Access Limitation: —
- **PF**: PDU format. Type: byte. Access Limitation: —
- **Characteristic**: Most significant byte of CAN ID (in CAPL the CAN ID is represented as a 32-bit value). The three most significant bits should have the value 100b if CAN ID is to be a valid Extended CAN Identifier. The five least significant bits represent priority (PRIO), extended data page (EDP) and data page (DP) of the CAN ID.
  - Bit 7: 1
  - Bit 6: 0
  - Bit 5: 0
  - Priority
  - EDP
  - DP
  Type: byte. Access Limitation: —
- **PRIO**: Priority of the parameter group. Type: byte. Access Limitation: —
- **DP**: Data page of the parameter group. Type: byte. Access Limitation: —
- **EDP**: Extended Data page of the parameter group. Type: byte. Access Limitation: —
- **NAME**: (unqualified) symbolic name of the message from the database (since version 7.2). Type: char[]. Access Limitation: read-only
- **DIR**: Direction of transmission, event classification; possible values: Rx, Tx, TXREQUEST. Type: byte. Access Limitation: —
- **RTR**: Remote Transmission Request; possible values: 0 (no RTR), 1 (RTR). Type: byte. Access Limitation: —
- **TYPE**: Combination of DIR and RTR for an efficient evaluation. `(TYPE = (RTR << 8) | DIR)`. Type: word. Access Limitation: —
- **TM**: Transmission Method
  - 0 = Single Frame (CAN and CAN FD)
  - 1 = C-PG within Multi-PG (CAN FD)
  - 2 = FD Transport Protocol (CAN)
  - 4 = Fast Packet Protocol (CAN)
  - 8 = J1939 Transport Protocol or Extended Transport Protocol (CAN)
  Type: byte. Access Limitation: —
- **DLC**: Data length in bytes. Value range: 0..1785. Type: byte. Access Limitation: —

### Message Times

- **TIME_NS**: Point in time, units: nanoseconds. Type: int64. Access Limitation: read-only
- **TIME**: Point in time, units: 10 microseconds. This selector is not available when executing CAPL code directly on network interfaces. Therefore you must use Time_ns. Type: dword. Access Limitation: —

### Flags

- **SIMULATED**: Message has been sent by a simulated CAPL node; possible values: 0 (no), 1 (yes). Type: byte. Access Limitation: —

### CAN FD Flags

- **FDF**: FD Format Indicator
  - 0 = Classic CAN message
  - 1 = CAN FD message
  Type: byte. Access Limitation: —
- **ADT**: Assurance Data Type. Value range: -1..255. Default value: -1 (undefined). For a parameter group transmitted using FD Transport Protocol, ADT corresponds to the Assurance Data Type field of the FD.TP.EndOfMsgStatus message. For all other messages this selector is not used. In J1939-22 following values or specified:
  - 0: No assurance data (default)
  - 1: Manufacturer specific cybersecurity assurance data
  - 2: Manufacturer specific functional safety assurance data
  - 3: Manufacturer specific combined cybersecurity followed by functional safety assurance data
  - 4..255: Reserved
  Type: int. Access Limitation: —
- **TOS**: Type of Service. Value range: -1..7. Default value: -1 (undefined). For a parameter group transmitted as a C-PG with a Multi-PG, TOS corresponds to the Type of Service in the Service Header of the C-PG. Type of Service and Trailer Format Value specify the type of assurance data used in the C-PG. In J1939-22 following values or specified:
  - 1 (001b) / 1 (001b): 32-bit manufacturer specific (OEM) cybersecurity assurance data
  - 1 (001b) / 2 (010b): 32-bit manufacturer specific (OEM) functional safety assurance data
  - 1 (001b) / 3 (011b): 32-bit manufacturer specific (OEM) cybersecurity followed by a 32-bit manufacturer specific (OEM) functional safety assurance data
  - 1 (001b) / 5 (101b): 64-bit manufacturer specific (OEM) cybersecurity assurance data
  - 1 (001b) / 6 (110b): 64-bit manufacturer specific (OEM) functional safety assurance data
  - 2 (010b) / 0 (000b): SAE J1939 with no assurance data
  - All other values: Not defined
  Type: int. Access Limitation: —
- **TF**: Trailer Format Value. Value range: -1..7. Default value: -1 (undefined). For a parameter group transmitted as a C-PG with a Multi-PG, TF corresponds to the Trailer Format Value of the Service Header of the C-PG. Trailer Format Value and Type of Service specify the type of assurance data used in the C-PG. For possible value combinations see selector TOS. Type: int. Access Limitation: —
- **ADS**: Assurance Data Size. Value range: -1..255. Default value: -1 (undefined). Assurance Data Size of a C-PG or a PG transmitted via FD.TP. The assurance data is part of the PG payload and is located at the end of it. So, the ADS is smaller than data length (selector DLC). For more information how to use this selector see [Send and Receive Parameter Groups with CAPL](../../CANoeCANalyzer/J1939/J1939CANfd/1939CANfdPGcaplSendRec.md). Type: int. Access Limitation: —

### Data Access

- **byte(x)**: Message data byte (unsigned 8 bit); possible values for x*: 0…63. Type: byte. Access Limitation: —
- **word(x)**: Message data word (unsigned 16 bit); possible values for x*: 0…62. The index is byte-oriented; for example, word(1) references to the data beginning at byte 1 and consists of byte 1…2 (16 bit). Type: word. Access Limitation: —
- **dword(x)**: Message data word (unsigned 32 bit); possible values for x*: 0…60. The index is byte-oriented; for example, dword(1) references to the data beginning at byte 1 and consists of byte 1…4 (32 bit). Type: dword. Access Limitation: —
- **qword(x)**: Message data word (unsigned 64 bit); possible values for x*: 0…56. Type: qword. Access Limitation: —
- **char(x)**: Message data byte (signed 8 bit); possible values for x*: 0…63. Type: char. Access Limitation: —
- **int(x)**: Message data word (signed 16 bit); possible values for x*: 0…62. The index is byte-oriented; for example, int(1) references to the data beginning at byte 1 and consists of byte 1…2 (16 bit). Type: int. Access Limitation: —
- **long(x)**: Message data word (signed 32 bit); possible values for x*: 0…60. The index is byte-oriented; for example, long(1) references to the data beginning at byte 1 and consists of byte 1…4 (32 bit). Type: long. Access Limitation: —
- **int64(x)**: Message data word (signed 64 bit); possible values for x*: 0…56. Type: int64. Access Limitation: —
- **float(x)**: Message data interpreted as IEEE float (32 bit); possible values for x*: 0…60. Type: double*. Access Limitation: —
- **double(x)**: Message data interpreted as IEEE double (64 bit); possible values for x*: 0…56. Type: double*. Access Limitation: —

## DA_TP or DA

A PDU2 **pg** does not actually need a destination address because it is broadcast. However, there is one exception: a PDU2 **pg** longer than 8 bytes is transmitted using the J1939 transport protocol. A J1939 transport protocol transmission also allows a destination address. This makes it possible to send a PDU2 **pg** to a specific address instead of broadcast. You can define this concrete address by setting the attribute selector **DA_TP**.

The selector **DA_TP** determines the receiver of the parameter group if transport protocol is used.

If selector **DA** is set then selector **DA_TP** gets the same value. However changing selector **DA_TP** doesn't influence selector **DA** (to avoid modification of the PGN).

In an [on pg](EventProcedures/CAPLfunctionJ1939OnPG.md) procedure, in case of a **PDU1** message, both selectors provide always the same value. For **PDU2** messages only the selector **DA_TP** provides the address of the receiver, while the selector **DA** provides the group extension of the PGN.

## Default values of FDF and TM

In a J1939 database the message attribute **J1939PgAppearanceOnBus** describes how a PG is expected on the bus. Depended on the attribute value and the current bus system the selectors **FDF** and **TM** are set if a Parameter Group object (pg) is defined.

- **J1939PgAppearanceOnBus: CAN_Extended**
  - **BusType**: CAN or CAN FD
  - **Default value of FDF**: 0
  - **Default value of TM**: 0

- **J1939PgAppearanceOnBus: CANFD_Extended**
  - **BusType**: CAN or CAN FD
  - **Default value of FDF**: 1
  - **Default value of TM**: 0

- **J1939PgAppearanceOnBus: Default**
  - **BusType**: CAN
  - **Default value of FDF**: 0
  - **Default value of TM**: 0

  - **BusType**: CAN FD
  - **Default value of FDF**: 1
  - **Default value of TM**: 3

For PGs defined by **pg \*** or if there is no message attribute **J1939PgAppearanceOnBus** in the database, the default values of **FDF** and **TM** are the same as for J1939PgAppearanceOnBus=**Default**.
