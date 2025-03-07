# ISO11783 Node Layer Error Codes

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/CAPLfunctionsISONLErrorCodes.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » **ISO11783 Node Layer Error Codes**

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

## Error Class 4, System Errors

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

## General Error

- **Error Code:** -1
  - **Description:** General error
  - **Additional Parameter:** —

## File Server Error

- **Error Code:** -1000
  - **Description:** [Iso11783FSReadFile](Functions/CAPLfunctionIso11783fsreadfile.md) has read all files
  - **Additional Parameter:** —

- **Error Code:** -1001
  - **Description:** Unknown path
  - **Additional Parameter:** —

- **Error Code:** -1002
  - **Description:** Invalid path
  - **Additional Parameter:** —

- **Error Code:** -1003
  - **Description:** Path must be absolute
  - **Additional Parameter:** —

- **Error Code:** -1004
  - **Description:** Cannot open file
  - **Additional Parameter:** —

- **Error Code:** -1005
  - **Description:** Cannot read from file
  - **Additional Parameter:** —

- **Error Code:** -1006
  - **Description:** Cannot write to file
  - **Additional Parameter:** —

- **Error Code:** -1007
  - **Description:** Cannot close file
  - **Additional Parameter:** —

- **Error Code:** -1008
  - **Description:** Cannot delete file
  - **Additional Parameter:** —

- **Error Code:** -1009
  - **Description:** Cannot rename file
  - **Additional Parameter:** —

- **Error Code:** -1010
  - **Description:** Cannot create new directory
  - **Additional Parameter:** —

- **Error Code:** -1011
  - **Description:** Directory already exists
  - **Additional Parameter:** —

- **Error Code:** -1012
  - **Description:** Cannot move Write/Read-position
  - **Additional Parameter:** —

- **Error Code:** -1013
  - **Description:** Invalid handle
  - **Additional Parameter:** —

- **Error Code:** -1014
  - **Description:** Cannot read file information
  - **Additional Parameter:** —

- **Error Code:** -1015
  - **Description:** Cannot set file attribute
  - **Additional Parameter:** —

- **Error Code:** -1016
  - **Description:** Directory could not be read
  - **Additional Parameter:** —

## Object Pool API Error

- **Error Code:** -1100
  - **Description:** Service not available
  - **Additional Parameter:** —

- **Error Code:** -1101
  - **Description:** Cannot change state of the node layer
  - **Additional Parameter:** —

- **Error Code:** -1102
  - **Description:** Response for function xy was not received or the response reports an error
  - **Additional Parameter:** ID of the function or error of a response

- **Error Code:** -1103
  - **Description:** Timeout: status message from VT not received for 3 seconds
  - **Additional Parameter:** —

- **Error Code:** -1104
  - **Description:** Information not available
  - **Additional Parameter:** —

- **Error Code:** -1105
  - **Description:** Timeout: Working Set Master/Member PG was not transmitted
  - **Additional Parameter:** —

- **Error Code:** -1106
  - **Description:** Invalid data is used
  - **Additional Parameter:** offset of the invalid data in the message

- **Error Code:** -1107
  - **Description:** Cannot open a file
  - **Additional Parameter:** —

- **Error Code:** -1108
  - **Description:** Invalid value is used
  - **Additional Parameter:** —

- **Error Code:** -1109
  - **Description:** Write access failed because attribute is read-only
  - **Additional Parameter:** —

- **Error Code:** -1110
  - **Description:** Invalid object ID is used
  - **Additional Parameter:** —

- **Error Code:** -1111
  - **Description:** Invalid attribute ID is used
  - **Additional Parameter:** —

- **Error Code:** -1112
  - **Description:** Object has not string value
  - **Additional Parameter:** —

- **Error Code:** -1113
  - **Description:** Unknown property or invalid property value is used
  - **Additional Parameter:** —

- **Error Code:** -1114
  - **Description:** Object has no numeric value
  - **Additional Parameter:** —

- **Error Code:** -1115
  - **Description:** Receive NACK from VT and restart initialization
  - **Additional Parameter:** —

- **Error Code:** -1116
  - **Description:** Unknown object ID is used
  - **Additional Parameter:** —

- **Error Code:** -1117
  - **Description:** An error is detected while reading the object pool
  - **Additional Parameter:** —

- **Error Code:** -1118
  - **Description:** The object is not supported for the current VT version
  - **Additional Parameter:** type of the object

- **Error Code:** -1119
  - **Description:** Invalid auxiliary assignment is used
  - **Additional Parameter:** source address of the auxiliary input device (VT version 2) or auxiliary function ID (VT Version 3)

- **Error Code:** -1120
  - **Description:** Timeout: auxiliary input maintenance message not received for inputs
  - **Additional Parameter:** auxiliary input ID

- **Error Code:** -1121
  - **Description:** No preferred auxiliary assignment available in this file
  - **Additional Parameter:** auxiliary input ID

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)