[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/CAPLfunctionsGNSSNLErrorCodesAppErrorIndication.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSS Node Layer Error Codes: GNSSAppErrorIndication**

# GNSS Node Layer Error Codes: GNSSAppErrorIndication

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

The error class and error codes of the [GNSSAppErrorIndication](Functions/CAPLfunctionGNSSapperrorindication.md) function are listed in the following table. The parameter `addInfo` is only valid for certain error messages.

## Error Class 1: Timeout

- **Error Code 0x01**: CTS error: There was no CTS for a RTS
- **Error Code 0x02**: The data was received after a timeout for a peer-to-peer connection.
- **Error Code 0x03**: The data received in the timeout during a BAM.
- **Error Code 0x04**: An EndOfMessage Acknowledge is missing or was received too late.

## Error Class 2: Address Claiming

- **Error Code 0x10**: The node has received an Address Claiming from another node and has to release its address for an ECU with higher priority.
- **Error Code 0x15**: Initialization error: The ECU name was assigned twice.
- **Error Code 0x17**: Initialization error: The ECU address was assigned twice. It should be noted that this error is only reported if the same CAN channel is used in addition to the name or address used twice.

## Error Class 4: System

- **Error Code 0x30**: An exception occurred during the protocol selection of BAM or CMDT.
- **Error Code 0x40**: The internal data buffer is occupied already.
- **Error Code 0x60**: The user is sending a System PG via the GNSS CAPL interface.

## Error Class 5: Transport Protocol

- **Error Code 0x71**: A transfer with the transfer protocol was interrupted by the receiver (the parameter `addInfo` contains the PGN).
- **Error Code 0x72**: A transfer with the transfer protocol was interrupted by the sender (the parameter `addInfo` contains the PGN).

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
