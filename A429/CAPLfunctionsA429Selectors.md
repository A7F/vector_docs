# ARINC Word Selectors

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## ARINC word selectors

- **Keyword**: `time`
  - **Description**: When an event handler ([on a429Word](EventProcedures/CAPLfunctionA429OnA429Word.md)/[on a429Worderror](EventProcedures/CAPLfunctionA429OnA429WordError.md)) is triggered, the time stamp of the event is stored in the selector. Unit: 10 µs
  - **Type**: `dword`
  - **Access Limitation**: read-only

- **Keyword**: `time_ns`
  - **Description**: When an event handler ([on a429Word](EventProcedures/CAPLfunctionA429OnA429Word.md)/[on a429Worderror](EventProcedures/CAPLfunctionA429OnA429WordError.md)) is triggered, the time stamp of the event is stored in the selector. Unit: nanoseconds
  - **Type**: `int64`
  - **Access Limitation**: read-only

- **Keyword**: `msgChannel`
  - **Description**: Transmission channel ([output](Functions/CAPLfunctionA429output.md)) or the channel which triggered an event handler ([on a429Word](EventProcedures/CAPLfunctionA429OnA429Word.md)/[on a429Worderror](EventProcedures/CAPLfunctionA429OnA429WordError.md)). Value range: 1..32
  - **Type**: `word`
  - **Access Limitation**: —

- **Keyword**: `ID`
  - **Description**: Label value. Value range: 0..255
  - **Type**: `dword`
  - **Access Limitation**: —

- **Keyword**: `name`
  - **Description**: Name of the ARINC word taken from the database (DBC)
  - **Type**: `char[]`
  - **Access Limitation**: read-only

- **Keyword**: `DIR`
  - **Description**: This direction is related to the corresponding event. A dedicated ARINC-429 channel may be either an Rx or Tx channel, but not both. Value range: Rx (default), Tx
  - **Type**: `byte`
  - **Access Limitation**: read-only

- **Keyword**: `parity`
  - **Description**: Overwrite the parity settings of a Tx channel for a specific ARINC word. The value may be changed with the function [a429SetParity](Functions/CAPLfunctionA429SetParity.md). Value range: 0: use channel configuration (default), 1: disable hardware parity support, 2: generate odd parity, 3: generate even parity
  - **Type**: `word`
  - **Access Limitation**: read-only

- **Keyword**: `TxCtrl`
  - **Description**: Define the scheduling type for the ARINC word with [a429SetScheduleTx](Functions/CAPLfunctionA429SetScheduleTx.md) and [a429StopTx](Functions/CAPLfunctionA429StopTx.md). Value range: 0: on request, 1: add to HW scheduler, 2: remove from HW scheduler
  - **Type**: `byte`
  - **Access Limitation**: read-only

- **Keyword**: `Error`
  - **Description**: The type of error is available in this field. [More detailed information about errors](../../CANoeCANalyzer/A429/basicsA429/A429ErrorDetection.md)
  - **Type**: `long`
  - **Access Limitation**: read-only

- **Keyword**: `simulated`
  - **Description**: If an ARINC event is detected this selector specifies whether the event was caused by CANoe DE product or not. Value range: 0: real event caused outside from the tool, 1: simulated event caused by the tool
  - **Type**: `byte`
  - **Access Limitation**: read-only

- **Keyword**: `TxCycle`
  - **Description**: This is the cycle time (in microseconds) which is given to the HW scheduler with [output](../CAN/Functions/CAPLfunctionOutput.md). The cycle time is set with [a429SetScheduleTx](Functions/CAPLfunctionA429SetScheduleTx.md).
  - **Type**: `dword`
  - **Access Limitation**: read-only

- **Keyword**: `FrameLen`
  - **Description**: Length of the detected ARINC word in nanoseconds.
  - **Type**: `dword`
  - **Access Limitation**: read-only

- **Keyword**: `BitRate`
  - **Description**: Detected bitrate for the ARINC word.
  - **Type**: `dword`
  - **Access Limitation**: read-only

- **Keyword**: `Gap`
  - **Description**: Specify the minimum distance to be kept for a scheduled ARINC word. This may be combined with the hardware scheduler. The gap may be set with [a429SetGap](Functions/CAPLfunctionA429SetGap.md) in combination with [a429CalcBitLength](Functions/CAPLfunctionA429CalcBitLength.md). The value is given in nanoseconds.
  - **Type**: `dword`
  - **Access Limitation**: read-only

## Data Access Selectors

- **Keyword**: `byte(x); char(x)`
  - **Description**: Access 8 bits in an ARINC word; x: 0..3
  - **Type**: —
  - **Access Limitation**: —

- **Keyword**: `word(x); int(x)`
  - **Description**: Access 16 bits in an ARINC word; x: 0..2
  - **Type**: —
  - **Access Limitation**: —

- **Keyword**: `dword(x); long(x)`
  - **Description**: Access 32 bits in an ARINC word; x: 0
  - **Type**: —
  - **Access Limitation**: —

The offsets used together with the selector address the following parts of the ARINC word.

- **Offset**: 3, 2, 1, 0
- **Byte(0)/char(0)**: 0
- **Byte(1)/char(1)**:
- **Byte(2)/char(2)**:
- **Byte(3)/char(3)**:
- **Word(0)/int(0)**: 0
- **Word(1)/int(1)**:
- **Word(2)/int(2)**:
- **Dword(0)/long(0)**: 0

[Meaning](../../CANoeCANalyzer/A429/basicsA429/A429basics.md): Parity + SSM + Data, Data, Data + SDI, ARINC-Label

**Bit number**: 32, 25, 24, 17, 16, 9, 8, 1
