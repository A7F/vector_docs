# J1939 CAPL Functions

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/CAPLfunctionsJ1939Overview.md)

**CAPL Functions** » **J1939** » J1939 CAPL Functions

**Valid for**: CANoe DE • CANoe4SW DE

Only available with [Option J1939](../../CANoeCANalyzer/J1939/J1939.md) and [Option ISO11783](../../CANoeCANalyzer/ISO11783/ISO11783.md).

---

**ON THIS PAGE:**

- [Diagnostic Trouble Code (DTC)](#J1939DTC)
- [Event Procedures](#EventProcedures)
- [Functional Safety — J1939-76 Dedicated SHM](#BMFunctionalSafetySHM)
- [Functional Safety — Messages With Integrated Checksum and Counter](#BMFunctionalSafetyCaC)
- [General](#General)
- [CAN FD — J1939-22](#BMcanFDJ1939-22)

## Diagnostic Trouble Code (DTC)

- **J1939GetDTC**: Function searches a J1939 diagnostic message for a DTC block containing the specified SPN/FMI/OC values.
- **J1939GetFmiFromDTC**: Function extracts FMI from DTC.
- **J1939GetNumOfDTCs**: Function returns the number of DTC blocks that match the search criteria.
- **J1939GetOcFromDTC**: Function extracts OC from DTC.
- **J1939GetSpnFromDTC**: Function extracts SPN from DTC.
- **J1939MakeDTC**: Function generates a DTC from the defined SPN, FMI and OC.

## Event Procedures

- **on pg**: Receives a J1939 specific message.

## Functional Safety — J1939-76 Dedicated SHM

- **J1939CalculateCrcOfSDM**: Calculates CRC for payload of a Safety Data Message.
- **J1939FillSHM**: Fills payload of a Safety Header Message with data of Safety Data Message.
- **J1939ParseSHM**: Provides data of the SDM message, which are contained in payload of the SHM message.

## Functional Safety — Messages With Integrated Checksum and Counter

- **J1939CalcChecksum**: Calculates the checksum of a parameter group.
- **J1939GetChecksumAndCounter**: Stores the checksum and counter of the parameter group in the given arguments.
- **J1939SetChecksumAndCounter**: Calculates and sets the checksum and the given counter to the parameter group.

## General

- **J1939ConvertMessageToPg**: Converts a CAN message to a J1939 parameter group.
- **J1939ConvertPgToMessage**: Converts a J1939 parameter group to a CAN message.
- **J1939GetAddress**: Gets the current address of a J1939 node even the address has been changed by the J1939 network management.
- **J1939GetDataPage**: Returns the [data page](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) bit of a parameter group or CAN ID.
- **J1939GetDestAddress**: Returns the value of the [PDU specific](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) field of a parameter group or CAN ID.
- **J1939GetDeviceName**: Gets the J1939 NAME as reported on the bus.
- **J1939GetPGN**: Returns the [parameter group number (PGN)](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group or CAN ID.
- **J1939GetPrio**: Returns the J1939 [priority](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group or CAN ID.
- **J1939GetSourceAddress**: Returns the [source address](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group or CAN ID.
- **J1939InitPGData**: Sets all data bytes of the parameter group to 255.
- **J1939IsPDU1**: Checks if the parameter group number (PGN) contained in the CAN ID has the [PDU Format 1](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md).
- **J1939IsPDU2**: Checks if the parameter group number (PGN) contained in the CAN ID has the [PDU Format 2](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md).
- **J1939MakeCanId**: Assembles a CAN ID from several J1939 fields.
- **J1939SetDatapage**: Sets the [data page](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group.
- **J1939SetDestAddress**: Sets the [PDU specific](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) field of a parameter group or CAN ID.
- **J1939SetPrio**: Sets the [priority](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group or CAN ID.
- **J1939SetSourceAddress**: Sets the [source address](../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group.
- **output**: Outputs a parameter group onto the CAN bus.

## CAN FD — J1939-22

- **J1939InitializeMultiPG**: Initiates a CAN FD message for use as a multiPG.
- **J1939AddContainedPG**: Adds an additional containedPG to a multiPG message.
- **J1939CheckMultiPG**: Checks whether a J1939-22 Multi-PG is consistent.
- **J1939GetContainedPG**: Get a Contained PG.
- **J1939GetContainedPGData**: Get PG Data of a Contained-PG.
- **J1939GetContainedPGAssuranceData**: Get assurance data of a Contained-PG.
- **J1939GetNumberOfContainedPGs**: Get the number of Contained-PGs (C-PGs) of a J1939-22 Multi-PG.

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
