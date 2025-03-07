# J1939 Node Layer Error Codes

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/CAPLfunctionsJ1939NLErrorCodes.md)

**CAPL Functions** » **J1939** » **J1939 NL** » J1939 Node Layer Error Codes

Valid for: CANoe DE • CANoe4SW DE

## Error Class 0: API Error

- **Error Number:** 0001h
  - **Error Code:** 000001h
  - **Description:** Is not allowed to call this function from a callback.
  - **Additional Parameter:** —

- **Error Number:** 0002h
  - **Error Code:** 000002h
  - **Description:** Invalid Handle
  - **Additional Parameter:** —

- **Error Number:** 0004h
  - **Error Code:** 000004h
  - **Description:** Invalid Parameter
  - **Additional Parameter:** —

- **Error Number:** 0005h
  - **Error Code:** 000005h
  - **Description:** Request cannot be sent
  - **Additional Parameter:** —

- **Error Number:** 0006h
  - **Error Code:** 000006h
  - **Description:** Unknown Environment Variable
  - **Additional Parameter:** —

- **Error Number:** 0007h
  - **Error Code:** 000007h
  - **Description:** Wrong Environment Variable Type
  - **Additional Parameter:** —

- **Error Number:** 0008h
  - **Error Code:** 000008h
  - **Description:** Parameter exceeds range
  - **Additional Parameter:** —

- **Error Number:** 0080h
  - **Error Code:** 000080h
  - **Description:** Internal Error
  - **Additional Parameter:** —

- **Error Number:** 0100h
  - **Error Code:** 000100h
  - **Description:** General Error
  - **Additional Parameter:** —

- **Error Number:** 0201h
  - **Error Code:** 000201h
  - **Description:** Unknown bus name
  - **Additional Parameter:** —

- **Error Number:** 0202h
  - **Error Code:** 000202h
  - **Description:** ECU is offline
  - **Additional Parameter:** —

- **Error Number:** 0203h
  - **Error Code:** 000203h
  - **Description:** Invalid address
  - **Additional Parameter:** —

- **Error Number:** 0204h
  - **Error Code:** 000204h
  - **Description:** Sender and receiver ECUs are on different buses
  - **Additional Parameter:** —

- **Error Number:** 0206h
  - **Error Code:** 000206h
  - **Description:** Output PG only for local ECU allowed
  - **Additional Parameter:** —

- **Error Number:** 020Bh
  - **Error Code:** 00020Bh
  - **Description:** ECU is not initialized correctly
  - **Additional Parameter:** —

- **Error Number:** 020Ch
  - **Error Code:** 00020Ch
  - **Description:** Invalid node layer context
  - **Additional Parameter:** —

## Error Class 1: Timeout Error

- **Error Number:** 1h
  - **Error Code:** 010001h
  - **Description:** CTS error - There was no CTS for an RTS.
  - **Additional Parameter:** PGN

- **Error Number:** 2h
  - **Error Code:** 010002h
  - **Description:** Data received after a timeout for a peer-to-peer connection
  - **Additional Parameter:** PGN

- **Error Number:** 3h
  - **Error Code:** 010003h
  - **Description:** Data received in the timeout during a BAM
  - **Additional Parameter:** —

## Error Class 2: Address Claiming Error

- **Error Number:** 10h
  - **Error Code:** 020010h
  - **Description:** The node has received an Address Claiming from another node and had to relinquish its address for an ECU with higher priority.
  - **Additional Parameter:** —

## Error Class 3: CAN Error

- **Error Number:** 01h
  - **Error Code:** 030001h
  - **Description:** Error while sending a message
  - **Additional Parameter:** —

## Error Class 4: System Error

- **Error Number:** 30h
  - **Error Code:** 040030h
  - **Description:** Exception during protocol selection of BAM or CMDT
  - **Additional Parameter:** —

- **Error Number:** 40h
  - **Error Code:** 040040h
  - **Description:** Internal data buffer occupied
  - **Additional Parameter:** —

- **Error Number:** 60h
  - **Error Code:** 040060h
  - **Description:** User is sending a System PG via the CAPL interface
  - **Additional Parameter:** —

## Error Class 5: Transport Protocol Error

- **Error Number:** 1h
  - **Error Code:** 050001h
  - **Description:** An invalid sequence number is used
  - **Additional Parameter:** PGN

- **Error Number:** 70h
  - **Error Code:** 050070h
  - **Description:** A transfer with the transfer protocol was interrupted by the receiver.
  - **Additional Parameter:** PGN or 0

- **Error Number:** 71h
  - **Error Code:** 050071h
  - **Description:** A transfer with the transfer protocol was interrupted by the sender.
  - **Additional Parameter:** PGN or 0

- **Error Number:** 72h
  - **Error Code:** 050072h
  - **Description:** General transport protocol error
  - **Additional Parameter:** PGN

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)